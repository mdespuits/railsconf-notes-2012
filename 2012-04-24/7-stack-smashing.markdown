# Stack Smashing

## Speaker: David Czarnecki
## [@czarneckid](http://twitter.com/czarneckid)
## [@agoragames](http://twitter.com/agoragames)
## [Slides](http://speakerdeck.com/u/czarneckid/p/railsconf-2012-stack-smashing-cornflower-blue)

### Infrastructure Insanity

* CEO Priority
* 1 month tour of duty
* Simplify (allthethings)
* Document (allthethings)
* app * __capacity__ -> 15 * 2 = 30 VMs
* VM profile:
  * 1 GB Ram
  * 40 GB disk
* MLG traffic #s
  * 4MM views
* quickly need a lot of VMs
* code stock (chef recipes)
* application migration
* start __internal__
* end __external__
* application upgrading
* Yada yada (the rest are all the slides)

### Server configuration

* does it make a sound?
* no, you get a phoen call

Gemify capistrano deployment

`gem 'capistrano-agora'`

### notify (allthethings)

Look into `geminabox-secure`

### Continuous deployment

### Github flow
* master is deployable
* features in branches
* post-build script trigger

### Recap

* Simplify, simplify, simplify
* Upgrade (small to big)
* Alias
* DRY
