# Android start project
A base android project where you can build up your awesome app.


## Notes

### Views
The View is usually not unit tested (unless you use Robolectric) so the fewer lines of code the better. Views should only know how to display data and send user events 
to the ViewModel (or Presenter). This is called the *Passive View pattern*.
Activities and fragments can be destroyed and created again.
:white_check_mark: Keep the logic in Activities and Fragments to a minimum

### ViewModel
Ideally, ViewModels shouldn’t know anything about Android. This improves testability, leak safety and modularity.
Conditional statements, loops and general decisions should be done in ViewModels or other layers of an app, not in the Activities or Fragments.
ViewModel is unaware in which state are Activities and fragments.


:white_check_mark: The recommended way to communicate between ViewModels and Views is the observer pattern, using LiveData or observables from other libraries.

### Repository
Repository modules handle data operations. They provide a clean API so that the rest of the app can retrieve this data easily. They know where to get the data from and 
what API calls to make when data is updated. You can consider repositories to be mediators between different data sources, such as persistent models, web services, and 
caches.
doesn't know how the data is fetched, so we can provide the view model with data obtained from several different data-fetching implementations.
Even though the repository module looks unnecessary, it serves an important purpose: it abstracts the data sources from the rest of the app. Now, our `ViewModel` 
