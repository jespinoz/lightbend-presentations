# CAP Theorem Revisited

---

**C**onsistency

- A read is guaranteed to return the most recent write for a given client

**A**vailability

- A non-failing node will return a reasonable response within a reasonable amount of time (no error or timeout)

**P**artition Tolerance

- The system will continue to function when network partitions occur

---

## Fallacies of Distributed Computing

The network is reliable.
Latency is zero.
Bandwidth is infinite.
The network is secure.
Topology doesn't change.
There is one administrator.
Transport cost is zero.
The network is homogeneous.

---

**CP** - Consistency/Partition Tolerance

- Unavailable in the face of a network outage
- Data consistency 
- Choose when atomic reads and writes are critical

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop_java/CAP-CP.png)

---

**AP** - Availability/Partition Tolerance

- Return the most recent version of the data you have (stale?)
- Accept writes that can be processed after partion resolves
- Flexibility around when the data in the system synchronizes

![inline](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop_java/CAP-AP.png)

---

## CP - Distributed cache

![left fit](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/distributed-cache-diagram-8243.pdf)

- Cache data that must be rendered with initial page load
- Cache for consistency, i.e, ensuring data remains consistent across nodes
- Essential to cache _mandatory data_ from _slow, unreliable, or third-party_ services

---

## AP - Instance-level cacheing

- Data will not remain consistent across nodes
- Use for data that must always be displayed but can be _eventually_ consistent

![right fit](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/instance-cache-diagram.pdf)

---

![right fit](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/page-zones-7915.pdf)

## Async page enhancement

- When caching isn't an option (e.g, third party web service integration)
- Slow or unavailable data sources can result in non-rendered page zones
- Manditory data used during initial rendering **must** be cached!

---

# Step 1 - Initial HTML rendering

1. Initial request
2. Dispatch to server
3. Request data
4. Render HTML and return

![left fit](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/html-flow-diagram-1-8066.pdf)

---

# Step 2 - Async enhancement

1. Render initial HTML
2. Load static assets from CDN
3. AJAX call from AngularJS
4. Request JSON from Play
5. Aggregate and compose
6. Return JSON, enhance page

![left fit](https://dl.dropboxusercontent.com/u/14279899/Deckset/play_workshop/html-flow-diagram-2-8339.pdf)
