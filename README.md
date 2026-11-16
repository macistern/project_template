# Plantilla de proyectos

Base común para crear proyectos con una forma consistente de desarrollar,
revisar, probar y desplegar. Este repositorio no es una aplicación: es la
fuente de las reglas y de los perfiles técnicos que se copian al proyecto.

## Crear un proyecto desde esta plantilla

1. En GitHub, abre este repositorio y pulsa **Use this template**.
2. Crea el repositorio nuevo, con el nombre y visibilidad del proyecto.
3. Elige un perfil de `templates/` y copia su contenido a la raíz del nuevo
   proyecto antes de escribir código. Por ejemplo, para Node/TypeScript:

   ```bash
   cp -R templates/node-typescript/. .
   ```

   El punto final es importante: también copia `.github/workflows/`.
4. Completa el README del producto, instala las dependencias y comprueba que
   el CI está verde.
5. Configura la protección de `main` indicada en `docs/ci-cd.md`.

Una plantilla copia archivos una vez: los proyectos creados no se actualizan
automáticamente si esta plantilla cambia.

## Perfiles disponibles

- `templates/node-typescript/`: Node.js, TypeScript y pnpm; incluye CI de
  calidad y build de una imagen Docker.
- `templates/python/`: punto de partida para Python. Se completa cuando se
  adopte su gestor de dependencias estándar.
- `templates/docker/`: convenciones de imagen y despliegue para servicios
  que ya tengan su propio stack.

## Documentos que gobiernan cada proyecto

- `AGENTS.md`: instrucciones operativas para asistentes y colaboradores.
- `docs/ci-cd.md`: política de ramas, calidad, releases y despliegues.
- `CONTRIBUTING.md`: flujo para contribuir y Definition of Done.

Las excepciones deben documentarse en el README del proyecto o en un ADR,
indicando motivo, responsable y fecha de revisión.
