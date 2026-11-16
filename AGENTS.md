# Reglas de ingeniería

Estas reglas aplican a todo el repositorio. Las instrucciones más específicas
de un subdirectorio pueden añadir restricciones, pero no reducir las de aquí.

## Entrega

- `main` debe permanecer en estado desplegable.
- No hacer push directo a `main`; todo cambio entra mediante Pull Request.
- Un cambio no está terminado sin las verificaciones disponibles y relevantes:
  formato, lint, tipos, pruebas y build.
- Añadir o actualizar pruebas ante cambios de comportamiento observable;
  incluir casos de error cuando el riesgo lo justifique.
- Mantener PRs pequeños, con un único objetivo y sin mezclar refactors ajenos.

## Seguridad y operaciones

- Nunca versionar secretos ni exponerlos en logs, artefactos o imágenes.
- Usar dependencias fijadas por lockfile y acciones de GitHub fijadas a una
  versión mayor conocida; actualizar dependencias en PRs separados.
- Los deploys de producción consumen un artefacto o imagen inmutable,
  identificada por versión o digest; no se usa `latest`.
- Para cambios de base de datos, usar migraciones compatibles hacia adelante
  y explicar impacto, orden de despliegue y rollback.
- Tras un despliegue, ejecutar healthcheck y smoke test antes de cerrarlo.

## Git

- Ramas: `feat/`, `fix/`, `chore/`, `docs/` y `release/`.
- Commits claros y atómicos; usar Conventional Commits cuando el proyecto lo
  configure.
- Preferir squash merge, salvo que el repositorio documente otra estrategia.
