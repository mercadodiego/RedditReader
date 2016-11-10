# Post Detail Assignment | Android Reddit Reader - Step 8

## Contexto

El presente curso ha sido diseñado por [Diego Mercado](https://github.com/mercadodiego) para la materia optativa _"Programación en Android: Introducción"_ de la Facultad de Astronomía, Matemática y Física (FaMAF) perteneciente a la Universidad Nacional de Córdoba, Argentina. 

## Objetivos

* Al seleccionar una celda de la lista, mostrar el detalle del post.

## Pre-Requsitos

* Haber completado la actividad de [endlessScrolling_assignment](https://github.com/mercadodiego/RedditReader/tree/endlessScrolling_assignment) 

## Enunciado 

### Primera parte

1-) Para "escuchar" por los eventos de selección de celda debe reimplementar el método `ListView.setOnItemClickListener(OnItemClickListener listener)`

2-) Emplear la siguiente interfaz para la comunicación entre `NewsActivity` y `NewsActivityFragment` 
  
```Java
public interface OnPostItemSelectedListener{
    void onPostItemPicked(PostModel post);
}
```

3-) La actividad de detalle debe llevar de nombre `ar.edu.unc.famaf.redditreader.ui.NewsDetailActivity`, con su correspondiente fragmento `ar.edu.unc.famaf.redditreader.ui.NewsDetailActivityFragment`

4-) Mostrar el título del post en un `TextView`


### Segunda parte

1-) Mostrar el siguiente detalle: 
* Subrredit al que pertenece
* Fecha
* Titulo 
* Usuario
* Preview (si está presente)
* Link a sitio web (si corresponde)

2-) Al seleccionar link el mismo debe abrir en una nueva actividad con una [WebView](https://developer.android.com/reference/android/webkit/WebView.html) que despliegue el contenido web, sin abandonar la aplicación 

## Tip

* Para poder emplear PostModel como parte del Intent, dicho objeto debe implementar la interfaz `Serializable` y emplear los métodos `putExtra(String name, Serializable value)` y `Serializable getSerializableExtra(String name)` de la clase `android.content.Intent`

## Condiciones generales de entrega

* **No deben emplearse frameworks que no sean los provistos oficialmente por la SDK de Android**
* Se debe trabajar en un repositorio GIT propio. Mayor información en: [Git-Basics-Working-with-Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
* La entrega consistirá en indicar en que TAG fue subido el mismo 
* No debe contener carpetas/archivos autogenerados
* Debe compilar. De lo contrario no será considerada como una entrega valida
* Debe desarrollarse usando Android Studio 2.2 (o cualquier versión superior del canal estable)
* Conservar Minimum SDK: API Level 15 y Target SDK: API Level 23 

## Licencia

* [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode)


