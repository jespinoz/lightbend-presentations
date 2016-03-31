# Play and Akka Together

---

# The Actor System in Play - how it is started and used

- Akka can work with several containers called _ActorSystems_
- An actor system manages the resources it is configured to use in order to run the actors which it contains

**Accessing the default Akka system:**

```java
ActorRef myActor = Akka.system().actorOf(Props.create(MyActor.class));
```

---

# Converting an Akka _Future_ to a Play _Promise_

- Note the Akka _ask_ pattern below

```java
import akka.actor.*;
import play.mvc.*;
import play.libs.Akka;
import play.libs.F.Promise;

import static akka.pattern.Patterns.ask;

public class Application extends Controller {

    public static Promise<Result> index() {
        ActorSelection actor = Akka.system().actorSelection("user/my-actor");
        return Promise.wrap(ask(actor, "hello", 1000))
                      .map(response -> ok(response.toString()));
    }
}
```

---

# For simple async computation, use a Promise instead of an Actor

```java
import play.libs.F.Promise;
import play.mvc.*;

import static play.libs.F.Promise.promise;

public class Application extends Controller {
    public static Promise<Result> index() {
        return promise(() -> longComputation())
                  .map((Integer i) -> ok("Got " + i));
    }
}
```

---

# Scheduling Tasks

- Send a message to _testActor_ every 30 minutes

```java
Akka.system().scheduler().schedule(
  Duration.create(0, TimeUnit.MILLISECONDS), //Initial delay 0 milliseconds
  Duration.create(30, TimeUnit.MINUTES),     //Frequency 30 minutes
  testActor,
  "tick",
  Akka.system().dispatcher(),
  null
);
```

---

# Scheduling Tasks 2

- Run this block of code 10 milliseconds from now

```java
Akka.system().scheduler().scheduleOnce(
  Duration.create(10, TimeUnit.MILLISECONDS),
  () -> file.delete(),
  Akka.system().dispatcher()
);
```
