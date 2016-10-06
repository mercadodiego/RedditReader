# ThreadsAssignment | Android Reddit Reader - Step 4

## Contexto

El presente curso ha sido diseñado por [Diego Mercado](https://github.com/mercadodiego) para la materia optativa _"Programación en Android: Introducción"_ de la Facultad de Astronomía, Matemática y Física (FaMAF) perteneciente a la Universidad Nacional de Córdoba, Argentina. 

## Objetivos

* Implementar una [AsyncTask](https://developer.android.com/reference/android/os/AsyncTask.html) dentro de una [ListView](https://developer.android.com/reference/android/widget/ListView) para ir descargando el contenido de las _thumbnails_ desde Internet 

## Pre-Requsitos

* Haber completado la actividad de [adapters_assignment](https://github.com/mercadodiego/RedditReader/tree/adapters_assignment) 

## Enunciado

1. La clase `ar.edu.unc.famaf.redditreader.ui.PostAdapter` debe implementar una AsyncTask que dada una URL previamente definida en la clase  `ar.edu.unc.famaf.redditreader.model.PostModel`, permita descargar dicha imagen y que sea parte de la ImageView representativa del *preview/thumbnail*
2. Debe emplearse un `android.widget.ProgressBar` animado mientras la imagen está siendo descargada 

## Condiciones generales de entrega

* Se debe trabajar en un repositorio GIT propio. Mayor información en: [Git-Basics-Working-with-Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
* La entrega consistirá en indicar en que TAG fue subido el mismo 
* No debe contener carpetas/archivos autogenerados
* Debe compilar. De lo contrario no será considerada como una entrega valida
* Debe desarrollarse usando Android Studio 2.2 (o cualquier versión superior del canal estable)
* Conservar Minimum SDK: API Level 15 y Target SDK: API Level 23 

## Licencia

* [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode)


