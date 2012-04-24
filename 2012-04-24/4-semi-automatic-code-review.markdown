# Semi Automatic Code Review

## Richard Huang

### About Me

* Work for GREE
  * OpenFeint platform
* OpenSource
  * create `rails_best_practices` gem

## Develop -> Review -> QA -> Merge -> Deploy -> Develop -> etc...

### Develop

* Manually Coding
* Automatic Unit Test

### Review

* Totally Manual

### QA

* Automatic Script Test
* Manually Verify

### Merge

* Automatic by Git
* Manually Fix conflicts

### Deploy

* Automatic by Capistrano

More less automatic everything in the whole process except around the __Review__ process.

#### Could automate review?

Yes, you can

### What to Review?

First Part:

* Follow coding guidelines
* Better coding syntax
* Remove unused methods

Second Part:

* Performant
* Scalable

What if we can review the first part automatically?

### How?

* `rails_best_practices` gem

### Integration

* Guard
* Jenkins
* Internal system

### Code Review Service

* [railsbp](http://railsbp.com)
  * automatically review
  * collaborate with co-workers
  * track history
  * configure what to review:w


