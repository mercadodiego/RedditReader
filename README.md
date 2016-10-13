# WebServices Assignment | Android Reddit Reader - Step 5

## Contexto

El presente curso ha sido diseñado por [Diego Mercado](https://github.com/mercadodiego) para la materia optativa _"Programación en Android: Introducción"_ de la Facultad de Astronomía, Matemática y Física (FaMAF) perteneciente a la Universidad Nacional de Córdoba, Argentina. 

## Objetivos

* Realizar una llamada a un servicio REST, interpretar el Json devuelto y mostrar los resultados en pantalla. 

## Pre-Requsitos

* Haber completado la actividad de [threads_assignment](https://github.com/mercadodiego/RedditReader/tree/threads_assignment) 

## Enunciado

1. Crear la clase `ar.edu.unc.famaf.redditreader.backend.GetTopPostsTask` que obtenga el contenido vía HTTP en formato JSon de los primeros 50 Top posts de Reddit, lo interprete y devuelva como resultado un `List<PostModel>`
2. El contenido debe mostrarse el la `ListView` de la clase `NewsActivityFragment`
3. Cuando no hay conexión a INTERNET mostrar un error que lo indique en forma de [AlertDialog](https://developer.android.com/reference/android/app/AlertDialog.html)
4. El interprete de JSON debe estar definido en una nueva clase `ar.edu.unc.famaf.redditreader.backend.Parser` y debe implementar el siguiente método de entrada, empleando internamente una instancia de [JsonReader](https://developer.android.com/reference/android/util/JsonReader.html) que devuelva una nueva clase llamada `ar.edu.unc.famaf.redditreader.model.Listing` (acorde a la estructura de objetos propia de la API de Reddit)
```Java
    public Listing readJsonStream(InputStream in) throws IOException {....}
``` 

## Tips

* La documentación oficial de la API de Reddit está disponible en [Reddit API](https://www.reddit.com/dev/api/)
* Para realizar una llamada REST HTTP (GET) puede emplear el siguiente snippet de código
```Java
    HttpURLConnection conn = (HttpURLConnection) new URL("...").openConnection();
    conn.setRequestMethod("GET");
    conn.getInputStream();
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


