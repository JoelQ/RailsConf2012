# Rails without Rails
## Piotr Sarnacki

* Rails 3.0+ is much more modular

### Action Controller
* inherits from Metal
* `https://gist.github.com/2482523`


### Good Design
* Reusable
* Decoupled
* A lot of APIs are just syntactic sugar over other APIs

### ActionView
* ::LookupContext finds the template
* ::Renderer renders the template
* Every view needs to be rendered with some kind of *context*
* ::Context (usually ::Base)
* Helpers not available by default when using only ActionView

### DIY
* Read the code
* Use a debugger
* Play with the code
* Crafting Rails Applications by Jose Valim

### Routers
* New router in Rails 3 called Journey

### Slides
* bit.ly/using-rails-without-rails
