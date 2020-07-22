#### Azure Event Grid
Event Grid aggregates all your events and provides routing from any source to any destination. Event Grid is a service that manages the routing and delivery of events from many sources and subscribers.
Event Grid is a simple but versatile event distribution system. Use it to deliver discrete events to subscribers, which will receive those events reliably and quickly. It is designed for one-event-at-a-time delivery.

![EventGrid](https://docs.microsoft.com/en-us/learn/modules/react-to-state-changes-using-event-grid/media/2-eventgrid-pub-sub.svg)

#### Capabilities
- Event filtering
- Support multiple subscribers
- Support built-in and custom events
- Reliable 24 hours

#### Concepts
- Events
- Event sources
- Topics
    - System topic
    - Custom topic
- Event subscriptions
- Event handlers

> Event Grid sends an event to indicate something has happened or changed. However, the actual object that was changed is not part of the event data. Instead, a URL or identifier is often passed to reference the changed object.

