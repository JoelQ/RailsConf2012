# Rails Engine Patterns
## Andy Maleh - 13:00

### Problem
* Monolithic app vs ecosystem
* Reusing functionality and components accross the ecosystem
* Duplicating features
* Rails engines - solution 

### Rails engines
* Break functionality into engines
* Extensible
* Removes duplication
* Engine is a ruby gem + MVC stack
* Allows reuse of assets, routes, rake tasks, mvc, tests, migrations, libraries

#### Anatomy of an engine
* An engine structure is similar to a rails app having app, config, lif, spec, features, etcs..
* config dir to simulate being an app to run tests
* lib just like a gem
* Use it like a gem in a Gemfile
* Typically, Rails loads files before engines
* This needs to be reversed
  * Monkey patch ActiveSupport
  * Config railties order (for > Rails 3.1)
  
### Ruby customization

* Customizations get mixed in to the app that have the same name
* Only keep the common minimum in the engine
* Images, assets and views don't get mixed in, they overwrite the engine

### Code management
* Each engine has own repo
* Each engine gets own gem dependency
* Make changes in engine, rake, and commit, obtaining a new GIT ref
* Update the gemfile and update the git ref
* Symlink the engine to the app for development
* `rake engine:symlink[engine_name]`
* Alternatively use local path

* Engines reuse engines
* With multiple levels, commit and bundle from the bottom up

* customize rack middleware, load paths, etc...
* namespace the engine
* keep the engine completely decoupled from the app, don't create a dependency back

## Rails engine patterns
### Goals
* keep engine code agnostic of app customizations
* prevent bi-directional coupling
* no app specific conditionals

### Common domain
* _Problem_: multiple apps need the same behaviour
* Include basic domain model (base bevaviour, common associations)
* Add app specific details in the apps
* Use `rails.application_routes.draw` for specific routes

### Expose Helper
* _Problem_: need to customize presentation logic in one app only but other apps share common logic
* Overwriting view is one solution but causes some duplication
* ???

### Expose Partial
* _Problem_: different customizations in one part of the view in multiple apps
* In engine extract custom part of view in a partial in the engine

### Extension Points
* _Problem_: multiple apps need to contruibute data to a view in different places
* In engine define helper that renders partials intelligently and inserts them in correct order. Partials exist in the app.

### Configurable Features
* _Problem_: different apps need different features in different combinations
* Engine has a config file and each app overides to get the necessary config options

## Pros/Cons
### Engine tradeoffs
* Overhead for building and maintaining an engine
* A lot of switching between engine and app during development (and a lot of bundling)
* Having to updgrade Gemfile

### Benefits
* code reuse accross all layers
* Better maintainability
* Offloading tests

### Engines vs Services
*Engines are better when:
  * reusing small mvc feartures
  * preffereing to avoid network  and infrastructure overhead
  * wanting to quickly extract and reuse a feature
* Engines vs Services are shades of gray
* Engines can be converted to services

*Services are better when:
  * reusing larger MVC components
  * need to consume feature in another programming languare
  * big need to scale
