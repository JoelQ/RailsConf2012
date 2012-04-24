# Evented ruby vs Node.js
## Jerry Cheung

### KISS performance
* lazy programming
* easy to implement, easy to maintain

### Evented Programming
* subscribing to events (i.e. js DOM events)
* Reactor pattern (callbacks sent to subscribers)
* User defined events
* Blocking I/O = slower devices that slow down a process
* CPU > Memory > Disc > Network
* Node manages I/O at the application level
* Blocking I/O decreases concurrency (i.e. database access)

* Using callbacks once a task has finished
* Move on to other taks
* Adds concurrency

### Evented Ruby vs Evented Javascript

