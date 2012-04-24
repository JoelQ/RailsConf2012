# Presenters and Decorators
## Mike Moore

### Presenters should ease pain
* They are there to solve a specific problem
* They do not need to be used early
* You should only change your typical approach when you feel pain

### Typical example
* Lots of partials
* Move view methods to the model
* Presentation vs Domain logic
* Move Presentation logic into a Presenter class
* Draper, ActiveDecorator are decorator libraries


### Rendering JSON
* Build serializer class with `to_json` method
* Easy to unit test
* ActiveModelSerializer simplifies even more


### Design Pattern?
* **Let your views be dumb**
* Decorator (GoF pattern)
* Mediator (object that encapsulates interactons between two objects, allows greater decoupling)
* Presenter Spectrum: 
* Models < ---- > Views
* Decorator < ----- > Presenters

### Rails Presenter Pattern
* Presentation model idea by Martin Fowler
* PM is an abstract of the view that is not dependant on a specific GUI implementation
* Presentation is a representation of the state of the view
* Identify decision points (i.e. Do I display categories?, If so, which ones?)
* Determining whether or not to show something should not be done by the view, use the presenter
