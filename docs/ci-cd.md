# Política de CI/CD

## Objetivo

Entregar cambios pequeños, trazables y reversibles. La calidad se comprueba
antes del merge; el mismo artefacto validado se promueve entre entornos.

## Ramas y merge

- `main` es la rama protegida y desplegable.
- Todo cambio llega desde una rama corta mediante Pull Request.
- Se requiere CI verde y una aprobación cuando participe más de una persona.
- Se usa squash merge para conservar una historia lineal y legible.
- No se omiten checks requeridos ni se hace push directo a `main`.

## CI obligatorio

Cada PR debe ejecutar, en este orden lógico:

1. Instalación reproducible desde lockfile.
2. Formato, lint y chequeo de tipos cuando apliquen.
3. Pruebas unitarias.
4. Pruebas de integración o E2E para los flujos críticos afectados.
5. Build de producción.
6. Build de la imagen Docker cuando el proyecto se despliegue como contenedor.

Las corridas de PR pueden cancelarse al recibir un commit nuevo. Las de `main`,
releases y deploys deben conservarse. Los secretos no se entregan a PRs desde
forks ni se guardan en cachés.

## CD

- Al mergear a `main`, desplegar automáticamente a staging si existe.
- Verificar staging mediante healthcheck y smoke test.
- Producción se promueve con aprobación explícita o con un tag `vX.Y.Z`.
- Producción usa exactamente el artefacto o imagen construida y verificada por
  CI; nunca se recompila en el servidor de destino.
- Un solo deploy simultáneo por entorno.
- Registrar versión, SHA de commit, fecha y responsable del deploy.

## Datos y rollback

- Las migraciones son versionadas, revisadas y compatibles hacia adelante.
- Antes de una migración de riesgo debe existir backup comprobable.
- Rollback de aplicación significa desplegar el artefacto anterior; las
  migraciones de datos no se revierten automáticamente.
- Todo release debe tener una versión anterior conocida a la que volver.

## Configuración inicial de GitHub

En `Settings → Rules → Rulesets`, proteger `main` con:

- pull request obligatorio;
- checks requeridos de CI;
- bloqueo de force push y borrado;
- aprobación requerida si hay equipo;
- ramas desactualizadas obligadas a ponerse al día antes del merge.
