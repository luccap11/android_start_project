# Android start project
A base android project where you can build up your awesome app.


## Notes

### Views
The View is usually not unit tested (unless you use Robolectric) so the fewer lines of code the better. Views should only know how to display data and send user events 
to the ViewModel (or Presenter). This is called the *Passive View pattern*.
:white_check_mark: Keep the logic in Activities and Fragments to a minimum

### ViewModel
Ideally, ViewModels shouldn’t know anything about Android. This improves testability, leak safety and modularity.
Conditional statements, loops and general decisions should be done in ViewModels or other layers of an app, not in the Activities or Fragments.
