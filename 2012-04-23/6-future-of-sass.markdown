# The Future of Sass

## Speaker: Hampton Catlin. [@hcatlin](http://twitter.com/hcatlin)

### Where I've Been

    "You used to do all this cool stuff before, then you just disapppeared."
    - [@ryancarson](htp://twitter.com/ryancarson) at FOWA

**Burn out :(**

* m.wikipedia.org => m.en.wikipedia.orgo
* Wikipedia Mobile was has 1.8 billion monthly pageviews
* Now at [Moovweb](http://site.moovweb.com/)

### Clear things up

#### .scss is the extension to Sass files
#### It's Sass not SASS

### Sass 3.2

* Placeholder Selectors
* Mixins -> "Blocks for CSS"
* @media craziness

### Load Paths

* `Sass.load_paths`
* Initialized via `ENV["SASS_PATH"]`
* Great for your shared library trove

* 1.8.7 is now the minimum
* `&foo` is gone
* `& foo` is A OK

### Thanks! (chuckle)

...one more thing

### Pros and Cons

#### Pros

* Mature
* Advanced
* Units, Functions, Selector, Inheritance

#### Cons

* Accessibility
* Speed

### Sass in C!

`libsass` by Aaron Leung [@akhleung](http://twitter.com/akhleung)

### Design
* C interface, C++ internals
* Statically linkable
* Small(ish)
* Simple interface
* FAST
* Sass 3.1 Features

### Development

* Sponsored by Mooveweb
* < 2 months in
* More features than we expected
* Adapters Needed!

### Stuff we do

* Mixins just work
* Variables
* Most Unit Conversions
* Simple interpolation
* Most functions
* Everything I use personally!

### In 0.2

* Selector INheritance: `@extends`
* Full Interpolation
* All units

### After that...

* Color functions
* Control Directives @if
* Callback API

### SassC

* Potentially up to 10,000% faster!!!!
* `./bin/sassc interpolation.scss > file.css`

### Why?

* Sass is awesome
* I made Haml for myself.
* It's powderful and it's beautiful.

### What can you do?

* Help with SassRuby
* Color functions!
* Evangelize
* Follow me on twitter [@hcatlin](http://twitter.com/hcatlin) and RT

# Link-gasm

* [libsasss](http://github.com/hcatlin/libsasss)
* [sassc](http://github.com/hcatlin/sassc)
* [sassruby](http://github.com/hcatlin/sassruby)
* [@hcatlin](http://twitter.com/hcatlin/)
* Discount Code: RailsConfCatlinSass2012
