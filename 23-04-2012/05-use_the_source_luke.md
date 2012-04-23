# Use the Source, Luke: High-fidelity history with even-sourced data
## Keith Gaddis - 14:30

### Event sourcing defined
* Application state changes encapsulated as events
* Events are serialized and stored
* Allows playback
* Commonly used with Domain Driven Design
* Active Record Models are not domain models

### Event Sourcing
* Events are applied to domain models
* applyiing the vent changes state
* listeners alsot take action on veents

### Event sourcing benefits
* Events are history of data
* Events allow you to recreate the state for any point in time
* Example: Account history
* Need to know what accounts look like as of a particular date
* rarely need to say "I'm sorry"
* bug fix by replaying events
* heavy/complex analytics
* Some reports can't be generated off normalized data
* Events are source of change
* Future requirements or changes in modeling

#### Modeling
* ES pushes mon domain logic oout of domain models
* System decoupling


### Drawbacks
* Overkill?
* Forces you to really analyze/know our problem
* Early in product development domain may be unclear
* Agility tradeoff - more constraints at first
* Performance
* Large event logs
* Store snapshot of domain models
* ActiveModel serialization is great for this

### Common use cases
* Source control
* Commits are events
* Financial/Accounting - get state an any point in time
* Complex domains
* Distributed systems, service oriented architectures


### Replay
* Replay gem
* facilitates event sources
* handles the event storage and application
* Allows other models to listen to vents on hte domain
* useful alone as part of CQRS

### Listeners
* Handle non-domain processes

### DCI
* Data Context Interaction
* Seperate domain models(data) from use cases(context) and role(interaction)
* Roles are modules that define actions/commands
* Lets us separate domain behaviour and domain data
* Mix in or compose roles into objects

### CQRS
* CQS Command Query Separation by Betrand Meyer
* Methods should either return value or mutate state
* CQRS Command Query Responsibility segregation
* Caries CQS to a system architecture
* domain models for application state
* Read models for system queries such as reporting
* command used (typicially objects) to change system
* commands generate events
* Events mutate state
* Easy to test

### More info
* Martin Fowler
* dddcqrs.com
* Domain Driven Design by Eric Evans
* karmajunkie.com
