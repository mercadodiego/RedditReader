# Persistence Assignment | Android Reddit Reader - Step 6

## Contexto

El presente curso ha sido diseñado por [Diego Mercado](https://github.com/mercadodiego) para la materia optativa _"Programación en Android: Introducción"_ de la Facultad de Astronomía, Matemática y Física (FaMAF) perteneciente a la Universidad Nacional de Córdoba, Argentina. 

## Objetivos

* Implementar una pequeña base de datos SQLite 

## Pre-Requsitos

* Haber completado la actividad de [webservices_assignment](https://github.com/mercadodiego/RedditReader/tree/webservices_assignment) 

## Enunciado

1. La clase `ar.edu.unc.famaf.redditreader.backend.GetTopPostsTask` debe implementar ahora el siguiente comportamiento
 1. Invocar al servicio REST de Reddit para obtener los primeros 50 TOP posts
 2. Persistir los resultados en una base de datos interna 
 3. Devolver los resultados desde la base de datos interna
 4. En caso de que no haya conexión a internet, se deben devolver los últimos resultados obtenidos desde la base de datos interna 
2. La base de datos interna debe estar implementada en una nueva clase: `ar.edu.unc.famaf.redditreader.backend.RedditDBHelper` de tipo `SQLiteOpenHelper`
 * Solo almacena los últimos 50 posts. El resto deben borrarse.
3. Los _thumbnails/preview_ a medida que se descargan deben también almacenarse. Recordar que pueden almacenarse como un arreglo de bytes:

```Java
   public static byte[] getBytes(Bitmap bitmap)
   {
        ByteArrayOutputStream stream=new ByteArrayOutputStream();
        bitmap.compress(CompressFormat.JPEG,0, stream);
        return stream.toByteArray();
   }
   public static Bitmap getImage(byte[] image)
   {
        return BitmapFactory.decodeByteArray(image, 0, image.length);
   }
```

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


