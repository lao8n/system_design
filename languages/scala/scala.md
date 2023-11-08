**Scala**

Functional data structures
* Functor = map
* Applicative functor = sequencing of functors
* Monad = map, flatMap & identity
* Monad transformer = monad that can stack

Errors
* Try (Try, Success, Failure) - bottling up exceptions and passing around across threads. 

Functional concepts
* Pure functions = 1. only depends on input variables 2. doesn't mutate any hidden state 3. no I/O 
* Tail-recursive functions = a function whose very last action is to call itself meaning we only ever need one stack frame
* Higher-order functions = functions that take other functions as an argument
* Call-by-value = evaluate arguments first so only evaluate arguments once - scala does this
* Call-by-name = reduce functions first and arguments second - as with `def`, should equivalent if pure functions and both evaluations termiante
* Currying = convert a function that takes multiple arguments into a pipeline of functions that takes one argument
* Implicits = involve compiler resolving type errors by using additional information in scope 1. implicit parameters = if method call does not supply all parameters 2. implicit converstions = supplied type does not match expected type 3. implicit classes = have type specific behaviour preserving abstract interface
* Covariance = about producers - producing something specific can satisfy a general requirement
* Contravariance = about consumer - consuming something general can satisfy specific requirement.

Reactive programming
* Question how to share updates that a signal has been re-evaluated
    1. Global data structure
    2. Synchronization
    3. Thread-local state
    4. Implicit parameters

Reactive streams = asynchronous stream processing with non-blocking back pressure to ensure the receiving side is not forced to buffer arbitrary amounts of data.

Language specifics
* Case class = optimzed for pattern matching where 1. immutable by default 2. comes with equals and hashCode methods 3. default apply method so don't need to use new keyword 4. unapply for pattern matching 5. getter same methods (class also has)
* Case objects = objects are singletons with extra benefits like 1. serializable 2. default hashCode implementation 3. toString implementation
* Traits = interfaces but with 1. concrete methods 2. can maintain state 3. have type parameters. They cannot be instantiated however. 