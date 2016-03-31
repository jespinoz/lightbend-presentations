# Akka Streams

---

# Akka Streams

- A library to express and run a chain of asynchronous processing steps acting on a sequence of elements
  - _DSL for async/non-blocking stream processing_
  - _Backpressure enabled by default_
  - _Implements the Reactive Streams spec for interoperability_
  - _Scala and Java APIs_

---

### Asynchronous boundary

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/microservices_wp/async/Page_3.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/microservices_wp/async/Page_4.jpg)

---

## Basics

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_01.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_02.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_03.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_04.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_05.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_06.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_07.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_08.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_09.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_10.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/flow-definition/Page_11.jpg)

---

# Materialization

Separates the _what_ from the _how_.

- Use Source/Flow/Sink to create a _blueprint_
- FlowMaterializer turns a blueprint into _Akka Actors_

![right fit](https://dl.dropboxusercontent.com/u/14279899/Blogs/reactive-streams/actors.png)

---

## Graphs

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/graph-shapes/Page_1.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/graph-shapes/Page_2.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/graph-shapes/Page_3.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/graph-shapes/Page_4.jpg)

---

## Flow control

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/starbucks/buffer/Page_1.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/starbucks/buffer/Page_2.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/starbucks/two-buffer-options/Page_1.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/starbucks/two-buffer-options/Page_2.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/starbucks/pull-based-backpressure/Page_1.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/starbucks/pull-based-backpressure/Page_2.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/starbucks/pull-based-backpressure/Page_3.jpg)

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/starbucks/pull-based-backpressure/Page_4.jpg)

---

## Advanced flow control

---

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/advanced-flow-control/Page_1.jpg)

--- 

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/advanced-flow-control/Page_2.jpg)

--- 

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/advanced-flow-control/Page_3.jpg)

--- 

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/advanced-flow-control/Page_4.jpg)

--- 

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/advanced-flow-control/Page_5.jpg)

--- 

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/nyc-reactive-streams/advanced-flow-control/Page_6.jpg)
