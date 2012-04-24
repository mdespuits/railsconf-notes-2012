# Evented Ruby vs Node.js
## Jerry Cheung [@whatcodecraves](http://twitter.com/whatcodecraves)

### Get performance benefits from Node into your Ruby apps

### KISS Performance

* User happy => I'm Happy
* Micro-optimizations are bad
* Easy to implement ,easy to maintain
* Minimize code an server infrastructure changes

### Overview

* Evented Programming
* Evented Web Backends
* Evented Ruby vs Evented Javascript
* Improving Rails Concurrency

### Javascript

* Reactors listen for events
* __Reactor Pattern__
  * Events: keyboard mouse, touch
  * Reusable reactors: browser, game loop
* Node.js
  * uses an event-drivern, non-blocking I/O
  * on top of concurrency; takes one step further; manages I/O at the application layer
* OS Switches processes

### Web Apps

* blocking I/O decreases concurrency
* database, filsystem - disk
* S3, external APIs - network
* ImageMagick - shelling out

### Evented Ruby

* ruby is capable of evented programming
* multi-paradism: procedural, evented, parallel
* mix and match paradigms

```ruby
EM.run {
  # tell the reactor to start running...
}
```

* Thin, Rainbows!, Passenger (w/patch)

```ruby
http = EM:HttpRequest.new('http://railsconf2012.com/').get
http.callback {
  # request finished
}
```

* App code aware of blocking I/O
* code doesn't look like ruby

### Procedural Interface, Evented Execution

```ruby
Faraday.default_adapter = :em_synchrony
response = Faraday.get 'http://railsconf2012.com'
```

* hides system event callbacks in libraries
* keeps app code clean

### Fiber Objects

* Fibers are primitives for implementing light weight __cooperative concurrency__ in Ruby.
* Code smell?
  * The main difference is that they are never preempted and that the __scheduling must be done by the programmer__ and not the VM

### Recap

* App server is reactor-aware
* One fiber per request
* App code is unchanged

### Starting Points

* data stores
* http
* `Kernel.system` calls

### Data stores

* redis
* mysql
* postgresql
* mongo

### HTTP

* Faraday: uses an EM-aware http adapter

### System Calls

* EM.popen - non-blocking version
* EM.deter - run blocking call outside of reactor thread

### Why Ruby?

* Resue existing code
* Performance won't be worse
* Keep procedural syntax
* Multi-paradigm

### Why Node?

* Single paradigm consistency
* Community

### Wrapping Up

* Evented programming is hard
* Evented programming for evented problems
* Evented programming doesn't fixx latency
* Avoid evented I/O in app code
