# Aaron Paterson - Keynote

## Failure
*I've made a huge mistake*

* Tokaido - binary ruby install
* How important is your time?
* Ecosystem (c extensions, etc)

### Failure to evolve
* Concurrency
* Why do we have `ActionMailer`
* Pull email out of the request/response process
* Producer/Consumer pattern
* Producer is a Queue which queues jobs then runs them (consumer)
* Implementation is secondary
* Producers must implement `push`, consumers must implement `run`
* We need a consistent API


### Failure to lead
* Fear of features
* Older developers have lower tolerance for technical debt
* Value is current + potential value
* Cost is Dev time + Mantenace
* Tolerance is value/time

#### Cosmetic Features
* Dubius value
* Unknown debt
* e.g. Tagged Logging (initially not thread safe)
* Why do we need this?

#### Refactoring Features
* High value
* Low debt
* Improve the architecture of our system
* e.g. Notifications
* refactored to include call-graphs
* Less code, more info, smaller stack

#### Course correcting feature
* High value
* unknown debt
* e.g. Asset pipeline
* too big to fail
* There is no bailout for technical debt

### Computation Distribution
* Centralized (terminal => Mainframe)
* Distributed (PC)
* Centralized (browser/server)
* Distributed (JS + Browser)
* Computation is moving to the browser

*We need to be prepared*
