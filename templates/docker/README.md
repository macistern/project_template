# Perfil Docker

Para un proyecto que ya tenga su stack, conservar las reglas comunes y añadir:

- `Dockerfile` reproducible y multi-stage cuando convenga.
- `.dockerignore` que excluya secretos, dependencias locales y builds.
- healthcheck real y endpoint de salud, si es un servicio.
- workflow de imagen que publique únicamente versiones inmutables.
