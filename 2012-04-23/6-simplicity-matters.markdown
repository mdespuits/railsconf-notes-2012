# Simplicity Matters

## Speaker: Chris Hickey (creator of Clojure)

    Simplicity is prerequisite for

### Word Origins

__Simple__

_Is_:

* One task
* One concept
* One dimension

_Not_:

* One instance
* One operation

__Easy__

* Near, at hand
* e.g. on our hard drive, in our tool set, IDE, apt-get, gem install...
* Near to our understanding/skill set
* Familiar
* Near our capabilities
* Easy is _relative_

### Limits

* We can only hope to make reliable those things we can understand
* We can only consier a few things at a time
* Intertwined things must be considered together
* Complexity undermines understanding


### Change

    Do more. Do it differently. Do it better.

* Changes to software require analysis and decisins
* You ability to reason about your program is critical
* More than tests, types, tools, process, etc...

### Simplicity = Opportunity

* Architectural Agility wins
* Otherwise, you end up pushing the elephant
* Design is about pullling things apart
* Repurpose, substitue, move, combine, extend...

    Programmers know the benefits of everything and the tradeoffs of nothing.

### Programmers vs Programs

* We focus on ourselvves
* Programmer convenience
* Programmer replaceability
* Rather than the programs
* Software quality, correctness
* Maintenance, change
* `gem install hairball`

    Be careful in choosing things you want to do. -Chris Hickey

### Complect

    To interleave, entwine, braid

* Don't do it!
* Complecting things is the sourse of complexity.

### Making Things Easy

* Bring to hand by installing
* Getting approved for use
* Become familiar by learning, trying
* But mental capability?
* not going to move very far

    We can be creating the exact same programs out of significantly simpler components.

### What's in _your_ Tookit?

This is wrong:

    Simplicity--the art of maximizing the amont of work not done--is essential.

### Lists and Order

* A sequence of thigns
* Does order matter?

```ruby
%w[first-thing second-thing third-thing] # order does not matter here...
```

### Why care about order?

* Complects each thing with the next
* Infects usage points
* Inhibits change
* "We don't do that"

### Maps (aka hashes)

* First class associative ata structures
* Idiomatic support
* Literals, accessors, symbolic keys

### Information _is_ simple

* Don't ruin it
* By hiding it behind a micro-language

### Encapsulation

* Is for implementation details
* Information doesn't have implementation
* Unless you added it - why?
* Information will have representation
* Have to pick one

### Can you move it?

* Litmus test - can move you your subsystems?
* Out of proc, different language, different thread?

### Subsystems Must have

* Well-defined boundaries
* Abstracted operational interface (Werbs)
* General error handling
* Take/return data
* `IPersonInfo` - oops!
* Again, maps {hashes}

### Simplicity is a Choice

* Requires vigilance, sensibilities and care
* Equating simplicity with ease and familiarity is wrong

    Develop sensibilities around entanglement.

### Simplitity __Matters__

* Complixity inhibits understanding and therefore robustness
* Simplicity enables hange
* It is the primary source of true agility
* Simplicity = Opportunity
