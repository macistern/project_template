# Cómo contribuimos

1. Actualiza `main` y crea una rama con el prefijo apropiado.
2. Implementa un cambio limitado y verifica los comandos definidos por el
   perfil del proyecto.
3. Abre un Pull Request con objetivo, evidencia de pruebas, riesgos y pasos
   de despliegue o rollback si corresponde.
4. Espera CI verde y revisión antes de hacer squash merge.

## Definition of Done

Un cambio está listo cuando:

- cumple formato, lint, tipos, pruebas y build aplicables;
- tiene pruebas proporcionales a su riesgo;
- no contiene secretos ni cambios no relacionados;
- documenta migraciones, flags, variables o cambios operativos;
- puede desplegarse y revertirse de forma segura.
