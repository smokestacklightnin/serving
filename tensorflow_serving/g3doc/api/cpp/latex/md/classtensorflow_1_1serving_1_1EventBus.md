::: {#classtensorflow_1_1serving_1_1EventBus}
:::

[\[classtensorflow\_1\_1serving\_1\_1EventBus\]]{#classtensorflow_1_1serving_1_1EventBus
label="classtensorflow_1_1serving_1_1EventBus"}

\#include $<$event\_bus.h$>$

Inheritance diagram for tensorflow::serving::EventBus$<$ E $>$:

![image](classtensorflow_1_1serving_1_1EventBus__inherit__graph.pdf){width="205pt"}

Collaboration diagram for tensorflow::serving::EventBus$<$ E $>$:

![image](classtensorflow_1_1serving_1_1EventBus__coll__graph.pdf){width="205pt"}

struct
[EventAndTime](#structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime)

*Event and the publish time associated with it.*

struct [Options](#structtensorflow_1_1serving_1_1EventBus_1_1Options)

class
[Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription)

using
[Callback](#classtensorflow_1_1serving_1_1EventBus_a5d602ec2a5a845d27799970475af24b9)
= std::function$<$ void(const
[EventAndTime](#structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime)
&)$>$

std::unique\_ptr$<$
[Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription)
$>$
[Subscribe](#classtensorflow_1_1serving_1_1EventBus_a39fe8c3ad82da890bdc4455dc05a43fb)
(const
[Callback](#classtensorflow_1_1serving_1_1EventBus_a5d602ec2a5a845d27799970475af24b9)
&callback) TF\_LOCKS\_EXCLUDED(mutex\_) TF\_MUST\_USE\_RESULT

[\[classtensorflow\_1\_1serving\_1\_1EventBus\_a29a951f5d7d4e6f7a85bf8d3b4c463f8\]]{#classtensorflow_1_1serving_1_1EventBus_a29a951f5d7d4e6f7a85bf8d3b4c463f8
label="classtensorflow_1_1serving_1_1EventBus_a29a951f5d7d4e6f7a85bf8d3b4c463f8"}
void
[Publish](#classtensorflow_1_1serving_1_1EventBus_a29a951f5d7d4e6f7a85bf8d3b4c463f8)
(const E &event) TF\_LOCKS\_EXCLUDED(mutex\_)

*Publishes an event to all subscribers.*

static std::shared\_ptr$<$
[EventBus](#classtensorflow_1_1serving_1_1EventBus) $>$
[CreateEventBus](#classtensorflow_1_1serving_1_1EventBus_abdf7f12c47dab911dfa5adbc8c3031c5)
(const [Options](#structtensorflow_1_1serving_1_1EventBus_1_1Options)
&options={})

### template$<$typename E$>$ class tensorflow::serving::EventBus$<$ E $>$ {#templatetypename-e-class-tensorflowservingeventbus-e .unnumbered}

[EventBus](#classtensorflow_1_1serving_1_1EventBus) enables basic
publish / subscribe semantics for events amongst one or more publishers
and subscribers. The purpose of
[EventBus](#classtensorflow_1_1serving_1_1EventBus) for serving is to
de-couple the code for such events, and is optimized for that use-case.

[EventBus](#classtensorflow_1_1serving_1_1EventBus) and Subscriptions
can be destroyed safely in any order. There is a strict requirement for
memory safety that a
[Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription)
must be destroyed before any of the objects or memory that a subscribers
callback accesses.

Important scaling and threading limitations:

Scaling: The [EventBus](#classtensorflow_1_1serving_1_1EventBus) is not
currently optimized for high scale, either in the number of subscribers
or frequency of events. For such use-cases, consider alternate
implementations or upgrades to this class.

Threading: [EventBus](#classtensorflow_1_1serving_1_1EventBus) is
thread-safe. However, if any subscriber callback calls any method in the
[EventBus](#classtensorflow_1_1serving_1_1EventBus), it will deadlock.
Subscribers are notified serially on the event publishers thread. Thus,
the amount of work done in a subscribers callback should be very
minimal.

This implementation is single-binary and does not communicate across
tasks.

Note that the types used for typename E in
[EventBus](#classtensorflow_1_1serving_1_1EventBus) must be moveable and
thread-safe. Future implementations may read Events of type E in
multiple threads.

[\[classtensorflow\_1\_1serving\_1\_1EventBus\_a5d602ec2a5a845d27799970475af24b9\]]{#classtensorflow_1_1serving_1_1EventBus_a5d602ec2a5a845d27799970475af24b9
label="classtensorflow_1_1serving_1_1EventBus_a5d602ec2a5a845d27799970475af24b9"}
template$<$typename E $>$\
using
[tensorflow::serving::EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
E
$>$::[Callback](#classtensorflow_1_1serving_1_1EventBus_a5d602ec2a5a845d27799970475af24b9)
= std::function$<$void(const
[EventAndTime](#structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime)&)$>$

The function type for
[EventBus](#classtensorflow_1_1serving_1_1EventBus) Callbacks to be
implemented by clients. Important Warnings:

Callbacks must not themselves callback to the
[EventBus](#classtensorflow_1_1serving_1_1EventBus) for any purpose
including subscribing, publishing or unsubscribing. This will cause a
circular deadlock.

Callbacks must do very little work as they are invoked on the publishers
thread. Any costly work should be performed asynchronously.

[\[classtensorflow\_1\_1serving\_1\_1EventBus\_abdf7f12c47dab911dfa5adbc8c3031c5\]]{#classtensorflow_1_1serving_1_1EventBus_abdf7f12c47dab911dfa5adbc8c3031c5
label="classtensorflow_1_1serving_1_1EventBus_abdf7f12c47dab911dfa5adbc8c3031c5"}

template$<$typename E $>$\
std::shared\_ptr$<$
[EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$ E $>$ $>$
[tensorflow::serving::EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
E $>$::CreateEventBus (

options = {}

)

Creates an [EventBus](#classtensorflow_1_1serving_1_1EventBus) and
returns a shared\_ptr to it. This is the only allowed public mechanism
for creating an [EventBus](#classtensorflow_1_1serving_1_1EventBus) so
that we can track references to an
[EventBus](#classtensorflow_1_1serving_1_1EventBus) uniformly.
[\[classtensorflow\_1\_1serving\_1\_1EventBus\_a39fe8c3ad82da890bdc4455dc05a43fb\]]{#classtensorflow_1_1serving_1_1EventBus_a39fe8c3ad82da890bdc4455dc05a43fb
label="classtensorflow_1_1serving_1_1EventBus_a39fe8c3ad82da890bdc4455dc05a43fb"}

template$<$typename E $>$\
std::unique\_ptr$<$ typename
[EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$ E
$>$::[Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription)
$>$
[tensorflow::serving::EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
E $>$::Subscribe (

callback

)

Subscribes to all events on the
[EventBus](#classtensorflow_1_1serving_1_1EventBus).

Returns a
[Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription)
RAII object that can be used to unsubscribe, or will automatically
unsubscribe on destruction. Returns a unique\_ptr so that we can use the
subscriptions address to Unsubscribe.

Important contract for unsubscribing (deleting the RAII object):

Unsubscribing (deleting the RAII object) may block while currently
scheduled callback invocation(s) finish.

Once it returns no callback invocations will occur. Callers destructors
must use the sequence: (1) Unsubscribe. (2) Tear down anything that the
callback references.

The documentation for this class was generated from the following file:

tensorflow\_serving/util/event\_bus.h
