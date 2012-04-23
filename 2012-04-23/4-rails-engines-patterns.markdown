# Rails Engines Patterns

## Speaker: Andy Maleh

*Dealing with the monolithic Rails app problems*

### What is a Rails Engine?

* Ruby Gem
* MVC Stack elements

That's it.

### Benefits of Rails Engines

* Extensible
* Removes duplication
* Shared code across applications
* Break the functionality into Rails Engines
* Re-use Models/View/Controllers/Helpers/etc.

### Engine Definition

* An engine structure is similar to a Rails app having app, config, lib, spec, features, etc.
* lib/engine_name.rb (read online instructions)
* lib/engine_name/engine.rb (read online instructions)

### Engine Consumption

Reference engine via Gemfile as  Ruby gem or Git repo hosted gemified project

### Goad Order

* Typically Rails app files load  first before Engine files
* Strong recommended to reverse so that engine's code is customizable per app
* Monkey patch ActiveSupport order to reverse the order

### Ruby Code customization

* Model/helper/controller behavior can be customized be redefining.rb files in Rails app
* Customizations get __mixed in__ with files in the Engine

### View and Asset Customization

* Engine View and Asset presentation can be customized by redefining files in Rails App
* Customizations __completely override__ files in Engine (ERB/Haml, Coffeescript, Sass, etc.)

### Code Management

* Each engine lives in own Repo independent of Rails App
* Each Engine gets its own Gem dependencies
* Make changes in engine, rake, and commit obtaining a new GIT ref
* Symlink engine path to Gemfile for fast development rather than committing numerous times for small fixes

### Improved Development Process

* Open Rails app and symlink all engines `rake engine` symlink
* Could use `:path` option in the Gem declaration in the Gemfile

### Engines Reuse Engines

* When multiple levels of depth are involved commit repos and update Gemfile from the bottom up.
* Example Engine 2 => Engine 1 => Rails App

### Engine Configuration

* Engines can be configured to customize rack middleware load paths, generators, and Rails component paths.

### Isolated Engines

* Avoid namespace clashing

### Rails Engine Patterns

_Goals_

* Keep engine code agnostic of app customizations
* Prevent bi-directional coupling to simplify reasoning about code
* Avoid app dependent conditionals to improve code maintainability

### 1. Pattern - Commin Domain

_Problem_

Multiple Rails aApps need to share a basic domain model includeing default CRUD and presentation behavior

_Solution_

* In engine, include basic domain models (base behavior, common associations) with their views, CRUD controllers, and routes.
* In each app, define domain model specialized behavior, exra assocations, and custom views.

### 2. Pattern - Expose Helper

_Problem_

* Need to customize presentation logic for a view 9 none app only, but keep the same logic in others
* This leads to duplication

_Solution_

* Remove custom view from Ap
* Use `requires_extended_address?` helper in Engine wherever the App used same logic

### 3. Pattern - Expose Partial

_Problem_

Need to have different customizations in one part oft the view in multiple apps

_Solution_

* Extract the view piece into a partial into the Engine
* No need for a helper.

### 4. Pattern - Extension Point

_Problem_

Multiple Apps need to contribute data to a View in different places. Engine defines only 3 elements in a list (About Me, News, and Noteworthy) and you need to insert an element in between.

_Solution_

* In Engine, add Helper logic that looks up partials in a specific order and based on file name insert into the right location in the View.
* In App, define these partials with the right file names and locations.

### 5. Pattern - Configurable Features

_Problem_

Configuration changes for one App but shared by all others

_Solution_

* Engine defines Yaml file for configuration
* App overrides some options in its own Yaml config file

### Engine Costs

* Overhead in establishing a new Rails Engine gem project
* Continuous switching between projcts and engines to get work done

### Rails Engine Benefits

* Code reuse across all application layers
* Better maintanability
* Independent project codebases
* Cleanly defined boundaries between projects and reusable components (engines)

### Engines vs. Services

__Engines are better when:__

* Reusing small MVC features, especially domain independent (e.g. Search Map)
* Preferring to avoiding network and infrastructure overhead over establishing a service
* Wanting to quickly extract and reuse a feature

__Services are better when:

* Reusing larger MVC features that depend on domain data
* Need to consume feature in another programming language or outside the organization boundaries

[@andymaleh](http://twitter.com/andymaleh)
