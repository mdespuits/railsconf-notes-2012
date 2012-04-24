# Presenters and Decorators: A Code Tour

## Speaker: Mike Moore [@blowmage](http://twitter.com/blowmage)

### Presenters should ease __PAIN__

* Solve a problem
* Presenters should not (necessarily) be used early

### Components...

* Be cognizant of the choices you are making.
* Think of the new developers (not newbies!)
* Don't be openly hostile to people unfamiliar with your app.

### View <=> Bikeshed

### Typical Summary Example...

* Lots of partials
* Move methods to the model
* Presentation vs Domain logic
* Move Presentation logic into own objects
* Draper, ActiveDecorator -> decorator libraries

### Serialization

* Move serialization and rendering into a separatr class which calls `to_json`
  * This approach is easy to unit test
* ActiveModel::Serializer

### Is that it?

* Have we really solved the whole problem?
* Problems in view are inheritly complex to deal with

### Presenter Definition

* How dumb can your templates be?
* Let your views be dumb

    Decorator Design Pattern - Attach additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.
    Mediator Design Pattern - Define an object that encapsulates how a set of objects interact. Mediator promotes loose coupling by keeping objects from referring to each other explicity, and lets you very ther interacti

### Presenter Spectrum

* One hand: _Models_. The other hand: _Views_
* Now you have Presenters <=> Decorators.

### Rails: Presenter Pattern

* [http://martinfowler.com/eaaDev/PresentationModel.html](http://martinfowler.com/eaaDev/PresentationModel.html)
* "Representation of the State of the View"
* `ViewModel` => Presentation Model

### A Good Example
