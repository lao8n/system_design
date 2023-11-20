**Akka**

Definition: long-running threads that respond to messages sent to them where the message are typically instances of immutable case classes and case objects

Code example
```
type Receive = PartialFunction[Any, Unit]
trait Actor {
  implicit val self: ActorRef // own address
  def receive: Receive
  def sender: ActorRef
  implicit val context: ActorContext
  ...
}
```

Error handling: Either 1. OneForOneStrategy 2. AllForOneStrategy

Concepts
* Selective receive = only retrieve messages that we are explictly interested in - leaving the others in the mailbox
* Backpressure = Reactive streams never emit more elements than the received total demand for any given subscriber. It tries to buffer elements until more demand is signalled, if overflow than drop the messages
* Akka classic vs Akka typed = Behaviour vs Actor, Behaviour.setup vs actorOf, and Behaviour vs become
