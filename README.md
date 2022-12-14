Git Workflow
============


La regla más importante de este workflow, es que el desarrollador que está escribiendo el código es responsable de asegurarse de que va a través de todo el proceso sin problemas y de manera oportuna.

Aunque esto pueda parecer un montón de pasos, es muy verboso y probablemente repite muchas cosas que ya estás haciendo. Por experiencia puedo decir que se convierte en algo muy natural después de un tiempo, y dejas de notarlo en absoluto.

Por supuesto, no hay una forma única y verdadera de trabajar con el código en todos los equipos, es un proceso interminable de mejora del flujo de trabajo existente. Ningún documento debería impedirte mejorar las cosas, y siempre deberías usar tu mejor criterio.

## New Code

### Create Branch

1. Actualizar las ramas **master**, **staging** y/o **feature** a la(s) última(s) versión(es)
  - Siempre rama desde el lugar que se fusionará de nuevo en
2. Cree una rama 
  - nombre corto y descriptivo
  - prefijado con las iniciales (ej. `tjk_branch_name`) en este caso solo usamos el dev

### Make Changes

3. Hacer el cambio
  - Asegúrese de que todas las tareas de vigilancia se están ejecutando (construcción, pruebas unitarias)
4. Prueba
  - Ejecute el conjunto de pruebas completo localmente
5. Confirmar con un nombre descriptivo
  - prefijo con `[WIP]` ("work in progress") si alguna prueba está rota  

### Push changes

6. Pull master para cualquier cambio
7. Rebase la rama en el maestro
8. Aplastar cualquier commit `[WIP]`.
    - Asegúrese de que todos los nombres de las confirmaciones tienen sentido para su contenido
    - No deje ningún commit roto
9. Empujar la rama a github
    - Crear una nueva rama de origen con el mismo nombre

### Pull Request

10. Abrir pull request en una rama **staging** o **feature**.
    - Título descriptivo más largo de la tarea
    - Viñetas con descripciones de los cambios (changelog)
11. El servidor de CI debe ejecutar pruebas en el pull request y actualizar su estado
    - (ej. Travis CI)

### Code Review

12. Otros desarrolladores deben revisar el código y dejar notas
    - no hay código confuso
    - comprobar los posibles problemas
    - cualquier mejora arquitectónica
    - el código está correctamente abstraído
    - asegurarse de que hay pruebas adecuadas

13. El propietario del código es responsable de realizar las correcciones necesarias y de subirlas
    - Seguir el mismo proceso de commit
14. Otros desarrolladores deben dar el visto bueno al código (al menos otros dos desarrolladores)
    - Dejar literalmente un comentario con un emoji de pulgar hacia arriba (`:+1:` en github)
    - Añade un texto corto de por qué estás de acuerdo con la fusión de la solicitud de extracción

### Code Review (alt)

Si hay que hacer un cambio rápido, uno que no afecte a ningún código real, o que tenga que salir rápidamente, se puede utilizar esta versión de revisión de código.

### Merging Code

Una vez que has tenido suficiente gente revisando, estás seguro del código que has escrito, y todo está bien probado y aprobado. Puedes comenzar el proceso de despliegue.

15. Fusiona el pull request en la rama **staging** o **feature**, y luego elimínalo en github.
16. Deja que el conjunto de pruebas completo se ejecute de nuevo en el código fusionado


## Additional Resources

- [A Successful Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/)
- [Understanding the Git Workflow](https://sandofsky.com/blog/git-workflow.html)
- [Github: Understanding the Git Flow](http://guides.github.com/overviews/flow/)
- [Issues with Git Flow](http://scottchacon.com/2011/08/31/github-flow.html)