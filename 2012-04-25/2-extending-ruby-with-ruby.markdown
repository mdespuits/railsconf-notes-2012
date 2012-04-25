# Extending Ruby with Ruby
## Speaker: Michael Fairley ([@michaelfairley](http://github.com/michaelfailey))

### Shoebox

### What does this mean?

* Metaprogramming in Ruby is really powerful

### Examples

* Haskell
* Python
* Scala

### 1. Python

* Function Decorators
  * So what?

    def fin(n)
      if n <= 1
        1 
      else
        fib(n - 1) * fub(n - 2)
      end
    end

    class Transactional < Decorator
      def call(orig, *args, &blk)
        ActiveRecord::Base.transaction do
          orig.call(*args, &bl)
        end
      end
    end

`gem install [method_decorators](http://github.com/michaelfairley/method_decorators)`

### Scala

* Partial application

Ruby :`[1,2,3].map { |i| i.to_s }` or `[1,2,3].map(&:to_s)`
Scala: `List(1,2,3).map(i => i.toString)` or `List(1,2,3).map(_.toString)`

New (bad) Ruby: `[1,2,3].map(&_{ _ + 1 })

    class Object
      def _(&blk)
        PartialApplication.new(blk)
      end
    end
    
    class PartialApplication
      def initialize(blk)
        @blk = blk
      end

      def to_proc
        lambda do |*args|
          Execution.new(args, @blk.binding).instance_eval(&@blk)
        end
      end
    end

### Haskell

* Lazy evaluation
