# Play

---

# Play Anatomy

![right fit](https://dl.dropboxusercontent.com/u/14279899/Deckset/chariot/play.jpg)

**Stateless**

- Session is stored in the browser cookie

**Actions**
  
- User-defined functions that run in a different _context_ than the request loop

---

# Play at its core

- Familiar MVC paradigm
- Embraces flows of data
    - WebSockets, SSE, Comet
    - Reactive Streams
    - File uploads
- Integration with Akka 
    - Distribute work via messaging
