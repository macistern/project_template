# Perfil Node.js + TypeScript + pnpm

Copia los archivos de este directorio a la raíz del nuevo proyecto. Este perfil
asume que el proyecto define en `package.json` los scripts:

```text
format:check  lint  typecheck  test  build
```

También requiere `packageManager` con una versión de pnpm y un `pnpm-lock.yaml`
commiteado. Antes de proteger `main`, instala dependencias y confirma que el
workflow de CI termina en verde.

Para un servicio en contenedor, añade un `Dockerfile` y conserva el workflow
`imagen.yml`: construye en cada PR y publica solo con tags `vX.Y.Z`.
