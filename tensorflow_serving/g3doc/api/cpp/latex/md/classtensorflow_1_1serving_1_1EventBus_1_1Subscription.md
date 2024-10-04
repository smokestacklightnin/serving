::: {#classtensorflow_1_1serving_1_1EventBus_1_1Subscription}
:::

[\[classtensorflow\_1\_1serving\_1\_1EventBus\_1\_1Subscription\]]{#classtensorflow_1_1serving_1_1EventBus_1_1Subscription
label="classtensorflow_1_1serving_1_1EventBus_1_1Subscription"}

\#include $<$event\_bus.h$>$

[\[classtensorflow\_1\_1serving\_1\_1EventBus\_1\_1Subscription\_a81795ea8fef03dd4240a753ccd532f7c\]]{#classtensorflow_1_1serving_1_1EventBus_1_1Subscription_a81795ea8fef03dd4240a753ccd532f7c
label="classtensorflow_1_1serving_1_1EventBus_1_1Subscription_a81795ea8fef03dd4240a753ccd532f7c"}
[$\sim$Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription_a81795ea8fef03dd4240a753ccd532f7c)
()

*Unsubscribes the subscriber.*

[\[classtensorflow\_1\_1serving\_1\_1EventBus\_1\_1Subscription\_afe4e553ef407bc9bbf2aadbf298be275\]]{#classtensorflow_1_1serving_1_1EventBus_1_1Subscription_afe4e553ef407bc9bbf2aadbf298be275
label="classtensorflow_1_1serving_1_1EventBus_1_1Subscription_afe4e553ef407bc9bbf2aadbf298be275"}
class **EventBus**

### template$<$typename E$>$ class tensorflow::serving::EventBus$<$ E $>$::Subscription {#templatetypename-e-class-tensorflowservingeventbus-e-subscription .unnumbered}

[Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription)
is an RAII object and tracks the lifecycle of a single subscription to
an [EventBus](#classtensorflow_1_1serving_1_1EventBus). Upon
destruction, it automatically Unsubscribes from the originating
[EventBus](#classtensorflow_1_1serving_1_1EventBus).

Note that
[Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription)
only maintains weak\_ptr references to the
[EventBus](#classtensorflow_1_1serving_1_1EventBus), such that the
[EventBus](#classtensorflow_1_1serving_1_1EventBus) and Subscriptions
can be safely destructed in any order.
[Subscription](#classtensorflow_1_1serving_1_1EventBus_1_1Subscription)
is not an owner of [EventBus](#classtensorflow_1_1serving_1_1EventBus).

The documentation for this class was generated from the following file:

tensorflow\_serving/util/event\_bus.h
