# Endless Scrolling Assignment | Android Reddit Reader - Step 7

## Contexto

El presente curso ha sido diseñado por [Diego Mercado](https://github.com/mercadodiego) para la materia optativa _"Programación en Android: Introducción"_ de la Facultad de Astronomía, Matemática y Física (FaMAF) perteneciente a la Universidad Nacional de Córdoba, Argentina. 

## Objetivos

* Implementar un scroll infinito donde se vayan mostrando 5 posts y mientras tanto se vayan obteniendo los próximos 5 posts.

## Pre-Requsitos

* Haber completado la actividad de [persistence_assignment](https://github.com/mercadodiego/RedditReader/tree/persistence_assignment) 

## Enunciado


1-) Implementar el siguiente método en nuestra clase `ar.edu.unc.famaf.redditreader.backend.Backend`
```Java
public void getNextPosts(final PostsIteratorListener listener) {...}
```

... donde `PostsIteratorListener` es:
 
```Java
public interface PostsIteratorListener {
    void nextPosts(List<PostModel> posts);
}
```
* La misma debe invocar al método nextPosts devolviendo los próximos 5 posts. Internamente la primera vez consulta al servicio web y persiste los primeros 50 resultados. Una vez que llega a dicho límite debe consultar por los próximos 50 posts y así sucesivamente.
 
2-) Crear la clase `ar.edu.unc.famaf.redditreader.backend.EndlessScrollListener`: 
```Java
import android.widget.AbsListView; 

public abstract class EndlessScrollListener implements AbsListView.OnScrollListener {
	// The minimum number of items to have below your current scroll position
	// before loading more.
	private int visibleThreshold = 5;
	// The current offset index of data you have loaded
	private int currentPage = 0;
	// The total number of items in the dataset after the last load
	private int previousTotalItemCount = 0;
	// True if we are still waiting for the last set of data to load.
	private boolean loading = true;
	// Sets the starting page index
	private int startingPageIndex = 0;

	public EndlessScrollListener() {
	}

	public EndlessScrollListener(int visibleThreshold) {
		this.visibleThreshold = visibleThreshold;
	}

	public EndlessScrollListener(int visibleThreshold, int startPage) {
		this.visibleThreshold = visibleThreshold;
		this.startingPageIndex = startPage;
		this.currentPage = startPage;
	}

	// This happens many times a second during a scroll, so be wary of the code you place here.
	// We are given a few useful parameters to help us work out if we need to load some more data,
	// but first we check if we are waiting for the previous load to finish.
	@Override
	public void onScroll(AbsListView view, int firstVisibleItem, int visibleItemCount, int totalItemCount) 
        {
		// If the total item count is zero and the previous isn't, assume the
		// list is invalidated and should be reset back to initial state
		if (totalItemCount < previousTotalItemCount) {
			this.currentPage = this.startingPageIndex;
			this.previousTotalItemCount = totalItemCount;
			if (totalItemCount == 0) { this.loading = true; } 
		}
		// If it's still loading, we check to see if the dataset count has
		// changed, if so we conclude it has finished loading and update the current page
		// number and total item count.
		if (loading && (totalItemCount > previousTotalItemCount)) {
			loading = false;
			previousTotalItemCount = totalItemCount;
			currentPage++;
		}
		
		// If it isn't currently loading, we check to see if we have breached
		// the visibleThreshold and need to reload more data.
		// If we do need to reload some more data, we execute onLoadMore to fetch the data.
		if (!loading && (firstVisibleItem + visibleItemCount + visibleThreshold) >= totalItemCount ) {
		    loading = onLoadMore(currentPage + 1, totalItemCount);
		}
	}

	// Defines the process for actually loading more data based on page
	// Returns true if more data is being loaded; returns false if there is no more data to load.
	public abstract boolean onLoadMore(int page, int totalItemsCount);

	@Override
	public void onScrollStateChanged(AbsListView view, int scrollState) {
		// Don't take any action on changed
	}
}
```
Fuente:  [guides.codepath.com](https://guides.codepath.com/android/Endless-Scrolling-with-AdapterViews-and-RecyclerView)

 * Nuestra `ListView` debe reimplementar [onScrollListener](https://developer.android.com/reference/android/widget/AbsListView.OnScrollListener.html) tal como indica la fuente y `NewsActivityFragment` implementar `PostsIteratorListener`. Una vez que haya nuevos resultados se debe invocar al método `notifyDataSetChanged()` de nuestro propio adapter. 

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


