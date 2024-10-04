::: {#top}
::: {#titlearea}
+-----------------------------------------------------------------------+
| ::: {#projectname}                                                    |
| My Project                                                            |
| :::                                                                   |
+-----------------------------------------------------------------------+
:::

::: {#main-nav}
:::

::: {#MSearchSelectWindow onmouseover="return searchBox.OnSearchSelectShow()" onmouseout="return searchBox.OnSearchSelectHide()" onkeydown="return searchBox.OnSearchSelectKey(event)"}
:::

::: {#MSearchResultsWindow}
:::

::: {#nav-path .navpath}
-   **tensorflow**
-   **serving**
-   [EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Types](#pub-types) \| [Public
Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1EventBus-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::EventBus\< E \> Class Template Reference
:::
:::
:::

::: {.contents}
`#include <event_bus.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::EventBus\< E \>:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1EventBus__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::EventBus\< E \>:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1EventBus__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[EventAndTime](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html){.el}

 

Event and the publish time associated with it.
[More\...](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html#details)\

 

struct  

[Options](structtensorflow_1_1serving_1_1EventBus_1_1Options.html){.el}

 

class  

[Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.el}

 

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------

using 

[Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.el}
= std::function\< void(const
[EventAndTime](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html){.el}
&)\>

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

std::unique\_ptr\<
[Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.el}
\> 

[Subscribe](classtensorflow_1_1serving_1_1EventBus.html#a39fe8c3ad82da890bdc4455dc05a43fb){.el}
(const
[Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.el}
&callback) TF\_LOCKS\_EXCLUDED(mutex\_) TF\_MUST\_USE\_RESULT

 

[]{#a29a951f5d7d4e6f7a85bf8d3b4c463f8} void 

[Publish](classtensorflow_1_1serving_1_1EventBus.html#a29a951f5d7d4e6f7a85bf8d3b4c463f8){.el}
(const E &event) TF\_LOCKS\_EXCLUDED(mutex\_)

 

Publishes an event to all subscribers.\

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

static std::shared\_ptr\<
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} \> 

[CreateEventBus](classtensorflow_1_1serving_1_1EventBus.html#abdf7f12c47dab911dfa5adbc8c3031c5){.el}
(const
[Options](structtensorflow_1_1serving_1_1EventBus_1_1Options.html){.el}
&options={})

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
### template\<typename E\> class tensorflow::serving::EventBus\< E \>

[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} enables
basic publish / subscribe semantics for events amongst one or more
publishers and subscribers. The purpose of
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} for serving
is to de-couple the code for such events, and is optimized for that
use-case.

[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} and
Subscriptions can be destroyed safely in any order. There is a strict
requirement for memory safety that a
[Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.el}
must be destroyed before any of the objects or memory that a
subscriber\'s callback accesses.

Important scaling and threading limitations:

Scaling: The
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} is not
currently optimized for high scale, either in the number of subscribers
or frequency of events. For such use-cases, consider alternate
implementations or upgrades to this class.

Threading: [EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}
is thread-safe. However, if any subscriber callback calls any method in
the [EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}, it
will deadlock. Subscribers are notified serially on the event
publisher\'s thread. Thus, the amount of work done in a subscriber\'s
callback should be very minimal.

This implementation is single-binary and does not communicate across
tasks.

Note that the types used for typename E in
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} must be
moveable and thread-safe. Future implementations may read Events of type
E in multiple threads.
:::

Member Typedef Documentation {#member-typedef-documentation .groupheader}
----------------------------

[]{#a5d602ec2a5a845d27799970475af24b9}

[[◆ ](#a5d602ec2a5a845d27799970475af24b9)]{.permalink}Callback {#callback .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename E \>
:::

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  using [tensorflow::serving::EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\< E \>::[Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.el} = std::function\<void(const [EventAndTime](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html){.el}&)\>
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
The function type for
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} Callbacks
to be implemented by clients. Important Warnings:

-   Callbacks must not themselves callback to the
    [EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} for any
    purpose including subscribing, publishing or unsubscribing. This
    will cause a circular deadlock.
-   Callbacks must do very little work as they are invoked on the
    publisher\'s thread. Any costly work should be performed
    asynchronously.
:::
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#abdf7f12c47dab911dfa5adbc8c3031c5}

[[◆ ](#abdf7f12c47dab911dfa5adbc8c3031c5)]{.permalink}CreateEventBus() {#createeventbus .memtitle}
----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename E \>
:::

+-----------------------------------+-----------------------------------+
|   ------------                    | [[static]{.mlabel}]{.mlabels}     |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- --- --------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------- ------------------ --- -- |                                   |
|   std::share                      |                                   |
| d\_ptr\< [EventBus](classtensorfl |                                   |
| ow_1_1serving_1_1EventBus.html){. |                                   |
| el}\< E \> \> [tensorflow::servin |                                   |
| g::EventBus](classtensorflow_1_1s |                                   |
| erving_1_1EventBus.html){.el}\< E |                                   |
|  \>::CreateEventBus   (   const [ |                                   |
| Options](structtensorflow_1_1serv |                                   |
| ing_1_1EventBus_1_1Options.html){ |                                   |
| .el} &    *options* = `{}`   )    |                                   |
|   ------------                    |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- --- --------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------- ------------------ --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Creates an [EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}
and returns a shared\_ptr to it. This is the only allowed public
mechanism for creating an
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} so that we
can track references to an
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el} uniformly.
:::
:::

[]{#a39fe8c3ad82da890bdc4455dc05a43fb}

[[◆ ](#a39fe8c3ad82da890bdc4455dc05a43fb)]{.permalink}Subscribe() {#subscribe .memtitle}
-----------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename E \>
:::

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --- --------------------------------------------------------------------------------------------------------- ------------ --- --
  std::unique\_ptr\< typename [EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\< E \>::[Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.el} \> [tensorflow::serving::EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}\< E \>::Subscribe   (   const [Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.el} &    *callback*   )   
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ --- --------------------------------------------------------------------------------------------------------- ------------ --- --
:::

::: {.memdoc}
Subscribes to all events on the
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.el}.

Returns a
[Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.el}
RAII object that can be used to unsubscribe, or will automatically
unsubscribe on destruction. Returns a unique\_ptr so that we can use the
subscription\'s address to Unsubscribe.

Important contract for unsubscribing (deleting the RAII object):

-   Unsubscribing (deleting the RAII object) may block while currently
    scheduled callback invocation(s) finish.
-   Once it returns no callback invocations will occur. Callers\'
    destructors must use the sequence: (1) Unsubscribe. (2) Tear down
    anything that the callback references.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/util/[event\_bus.h](event__bus_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
