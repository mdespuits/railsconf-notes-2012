# Designing Hypermedia APIs

## Speaker: Steve Klabnik

One day, I went searching for the meaning of REST.

### REST is over.

* Do not tell someone they are stupid if you want to change their minds or opinions.
* REST got bad branding.

### Hypermedia APIs

* Hypermedia is Transfering text documents that have links that connect them to the rest of the world.
* Hypermedia designs scale better, are more easily changed and promote decoupling and encapsulation, with all the benefits those things bring.
* On the downside, it is not necessarily thoe most latency-tolerant design, and caches can get stale if you are not careful. It may not be as efficient on an individual request level as other designs.

    "Rest is software design on the scale of decades; every detail is intended to promote software longevity and independent evolution. Many of the constraints are directly opposed to short-term efficiency. Unfortunately, people are faily good at short-term design, and usually awful at long-term design."

* **We fail at longevity and independent evolution.**
* **COUPLING IS THE ENEMY!!**

We need decoupling to handle the hugeness of the web network.

1. Use HTTP Properly*
2. Use Hypermedia to guide clients through business processes.

### Why HTTP?

* Client-Server
* Stateless
* Caching
* Uniform Interface
* Layered System
* Code-on-demand

`GET /photo/12/delete` is not right!

## Five steps of Hypermdeia API Design

1. Evaluate Business Prcesses
2. Create State Machine
3. Evaluate Media Types
4. Create Media Types
5. Implement!

* Build Hypermedia semantics on top of JSON.
* Build a format on top of JSON.
* Use a type already in existence.
* Media type design is just as much an art as it is a science.

Building an application type:

**w3clove.validation+json** => `application/vcd.w3clove.validation+json` is an example of a media type.

See [DesigningHypermediaAPIs.com](http://designinghypermediaapis.com) for more info.

[@steveklabnik](http://twitter.com/steveklabnik)
[Steve Klabnik](http://steveklabnik.com)
