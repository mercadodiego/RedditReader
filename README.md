# AdaptersAssignment | Android Reddit Reader - Step 3

## Contexto

El presente curso ha sido diseñado por [Diego Mercado](https://github.com/mercadodiego) para la materia optativa _"Programación en Android: Introducción"_ de la Facultad de Astronomía, Matemática y Física (FaMAF) perteneciente a la Universidad Nacional de Córdoba, Argentina. 

## Objetivos

* Implementar una [ListView](https://developer.android.com/reference/android/widget/ListView) que obtenga su contenido desde un propio [ArrayAdapter](https://developer.android.com/reference/android/widget/ArrayAdapter.html) 

## Enunciado

1. Descargar el tag "adapters_assignment" del repositorio https://github.com/mercadodiego/RedditReader
2. La clase `ar.edu.unc.famaf.redditreader.model.PostModel` representa un Post en Reddit. La misma ya está creada pero vacía, debe agregar los atributos relativos al título, autor, fecha de creación, numero de comentarios e imagen de *preview/thumbnail* con sus correspondientes *setter/getter*
3. Implementar el método `List<PostModel> getTopPosts()` de la clase `ar.edu.unc.famaf.redditreader.backend.Backend`. El mismo debe devolver siempre 5 instancias de `PostModel` con contenido falso o *dummy* 
4. Crear la clase `ar.edu.unc.famaf.redditreader.ui.PostAdapter` que extienda de `android.widget.ArrayAdapter` e re-implementar los métodos necesarios
5. `NewsActivityFragment` debe mostrar una [ListView](https://developer.android.com/reference/android/widget/ListView) que ocupe todo su espacio y debe desplegar el contenido de cada uno de los Posts siguiendo el diseño implementado en la actividad previa de [LayoutAssignment](https://github.com/mercadodiego/RedditReader/blob/layout_assignment/README.md). Tener en cuenta que el título debe poder siempre mostrarse y la altura de cada fila debe ajustarse para permitirlo
6. Implementar un *ViewHolder* en nuestra clase `ar.edu.unc.famaf.redditreader.ui.PostAdapter` para mejorar la performance de la [ListView](https://developer.android.com/reference/android/widget/ListView). Mayor información en: [Hold View Objects in a View Holder](https://developer.android.com/training/improving-layouts/smooth-scrolling.html#ViewHolder)

## Condiciones generales de entrega

* Se debe trabajar en un repositorio GIT propio. Mayor información en: [Git-Basics-Working-with-Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
* La entrega consistirá en indicar en que TAG fue subido el mismo 
* No debe contener carpetas/archivos autogenerados
* Debe compilar. De lo contrario no será considerada como una entrega valida
* Debe desarrollarse usando Android Studio 2.2 (o cualquier versión superior del canal estable)
* Conservar Minimum SDK: API Level 15 y Target SDK: API Level 23 
