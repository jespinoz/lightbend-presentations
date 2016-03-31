# Going Async

---

# Future coffee

**Synchronous coffee:**
1. Start coffee maker
2. Stay in in kitchen
3. Wait until coffee maker finishes
4. Pour and drink

![right](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/color-correct-coffee-cropped.jpg)

---

# Future coffee

**Asynchronous coffee:**
1. Start coffee maker
2. Leave the kitchen
3. Check your e-mails, etc
4. Hear the coffee maker finish
5. Return to kitchen
6. Pour and drink

![right](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/color-correct-coffee-cropped.jpg)

---

# Future coffee

Kitchen → _thread_
Cup of coffee → _task to be completed_
Coffee maker → _IO_

![right](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/color-correct-coffee-cropped.jpg)

---

# Asynchronous vs synchronous processing times

![right fit](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/asynch-vs-synch-timings-9554.pdf)

- Staying async — and in the future — ensures that processing time is not bounded by IO
- Async processing is limited by only the longest running process
- Synchronous processing is limited by the combined processing times

---

# Future[Result]

```scala
def index = Action.async {
  val futureInt = scala.concurrent.Future { intensiveComputation() }
  futureInt.map(i => Ok("Got result: " + i))
}
```

- Play actions are asynchronous by default
- Here, the body is actually an anonymous function

---

# Future[Result]

- **Future** provides a way to do asynchronous handling
    - Doesn't necessarily have to be non-blocking
- Allow the runtime to decide order of execution
- If a thread can't be deallocated while waiting for other systems to respond, then it is blocking
