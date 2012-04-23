# Use the Source, Luke: High-fidelity history with event-sourced data

## Speaker: Keith Gaddis

    [Event Sourcing] captures all changes to application state as a sequence of events. -[Martin Fowler](http://martinfowler.com/eaaDev/EventSourceing.html)

## Event Sourcing defined

* Application state changs encapsulated as events
* Events are serialized and stored, allowing playback of events later to recreate application state
* Snapshots of application state represent point-in-time
* Commonly used with Domain Driven Design (DDD) and a domain model

### Event-sourcing: state changes

* Events are _applied_ to domain models
* Applying the event changes state
* Listeners (observers) also take action on events

### Event sourcing benefits

* Events as history of data
* Using events you can recreate the applicaiton sate _at any point in time_
* Example: Account History
* Need to know what an account looked like as of the last billing date despite any transactions done since
* Never (rarely?) having to say "I'm sorry"
* Bugs: fix a bug, replay events, database is fixed
* Heavy/Complex Analytics
* Some reports may be in a non-normalized form
* Future requirements or changes in modeling

### Modeling

* ES pushes non-domain logic out of the domain models ( You _should_ be doing this anyway )
* System decoupling

### ES Drawbacks

#### 1. Overkill?
* Forces you to really analyze/know your problem
* Early in product development the domain may be unclear
* Agility tradeoff

#### 2. Performance
* Large events logs (thousands, even millions of events in some domains)
* Store snapshot of domain models
* `ActiveModel` serialization is great for this

### Common Use Cases

* Sourse control
* Every commit is an event
* Financial/Accounting systems
* Complex domains
* Distributed systems, services oriented architecture (SOA)

### Code example: Ordering System

Objects:

    class Order
      attr_accessor :order_id, :line_items

      def initialize(order_id)
        @order_id = order_id
        @line_items = []
      end
    end

    class LineItem
      attr_accessor :sku, :price

      def initialize(sku, price)
        @sku = sku
        @price = price
      end
    end

The events are determined in other PORC (plain old ruby classes) that trigger events (Redis for example).

### Introduction Replay

* Facilitates event-sourcing
* Handles the event storage and application
* Allows other models to listen to events on the domain
* Useful alone or as port of a CQRS architecture

### DCI (Data Context Interaction)

* Separates domain models (data) from use-cases (context) and role (interation).
* Roles are modules that define actions/commands
* Separate Domain Behavior from domain data
* Mix in or compose roles into objects (models) in the associated context

### CQRS

* Command Query Separation, introducted by Betrand Meyer.
* Command Query Responsibility Segregation, popularized by Udi Dahan and Greg Young
* Carries CQS to a system architecture
* Domain models for Application state
* "Read models" for system queries, such as reporting
* Commands (typically objects) used to change system
* Commands generate events, which mutate state and can be syndicated to distributed systems

### More Info:

* [Event Sourcing](http://martinfowler.com/eaaDev/EventSourcing) by Martin Fowler
* [dddcqrs.com](dddcqrs.com)
* Domain Driven Design, by Eric Evans
* [http://karmajunkie.com](http://karmajunkie.com)
