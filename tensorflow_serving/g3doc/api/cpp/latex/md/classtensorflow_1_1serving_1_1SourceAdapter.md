::: {#classtensorflow_1_1serving_1_1SourceAdapter}
:::

[\[classtensorflow\_1\_1serving\_1\_1SourceAdapter\]]{#classtensorflow_1_1serving_1_1SourceAdapter
label="classtensorflow_1_1serving_1_1SourceAdapter"}

\#include $<$source\_adapter.h$>$

Inheritance diagram for tensorflow::serving::SourceAdapter$<$ InputType,
OutputType $>$:

![image](classtensorflow_1_1serving_1_1SourceAdapter__inherit__graph.pdf){width="350pt"}

Collaboration diagram for tensorflow::serving::SourceAdapter$<$
InputType, OutputType $>$:

![image](classtensorflow_1_1serving_1_1SourceAdapter__coll__graph.pdf){width="350pt"}

void
[SetAspiredVersions](#classtensorflow_1_1serving_1_1SourceAdapter_a9775d0a39269efb319a0dbd94862f183)
(const StringPiece servable\_name, std::vector$<$
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$ InputType
$>$$>$ versions) final

[\[classtensorflow\_1\_1serving\_1\_1SourceAdapter\_aa123a0dc11c1c45073e16bb40ae50285\]]{#classtensorflow_1_1serving_1_1SourceAdapter_aa123a0dc11c1c45073e16bb40ae50285
label="classtensorflow_1_1serving_1_1SourceAdapter_aa123a0dc11c1c45073e16bb40ae50285"}
void **SetAspiredVersionsCallback** (typename
[Source](#classtensorflow_1_1serving_1_1Source)$<$ OutputType
$>$::[AspiredVersionsCallback](#classtensorflow_1_1serving_1_1Source_aeb281087e1478b0ff4a74e3f60496c6f)
callback) final

virtual std::vector$<$
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$
OutputType $>$ $>$
[Adapt](#classtensorflow_1_1serving_1_1SourceAdapter_a7c960f8493040fc8cb0766e4c2cebf60)
(const StringPiece servable\_name, std::vector$<$
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$ InputType
$>$$>$ versions)=0

[\[classtensorflow\_1\_1serving\_1\_1SourceAdapter\_acb3ad719a856c7bb0085df33438c4986\]]{#classtensorflow_1_1serving_1_1SourceAdapter_acb3ad719a856c7bb0085df33438c4986
label="classtensorflow_1_1serving_1_1SourceAdapter_acb3ad719a856c7bb0085df33438c4986"}
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$
OutputType $>$
[AdaptOneVersion](#classtensorflow_1_1serving_1_1SourceAdapter_acb3ad719a856c7bb0085df33438c4986)
([ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$
InputType $>$ input)

*Adapts a single servable data item. (Implemented on top of
[Adapt()](#classtensorflow_1_1serving_1_1SourceAdapter_a7c960f8493040fc8cb0766e4c2cebf60).)*

### template$<$typename InputType, typename OutputType$>$ class tensorflow::serving::SourceAdapter$<$ InputType, OutputType $>$ {#templatetypename-inputtype-typename-outputtype-class-tensorflowservingsourceadapter-inputtype-outputtype .unnumbered}

An abstraction for a module that receives aspired-version callbacks with
data of type InputType and converts them into calls with data of type
OutputType.

A common example uses InputType=StoragePath,
OutputType=unique\_ptr&lt;[Loader](#classtensorflow_1_1serving_1_1Loader)$>$,
in which case the module '̈converts'̈ each incoming storage path into a
loader capable of loading a (particular type of) servable based on the
path.

SourceAdapters are typically stateless. However, as with all Sources
they can house state that is shared among multiple emitted servables.
See the discussion in [source.h](#source_8h_source).

Implementing subclasses supply an implementation of the
[Adapt()](#classtensorflow_1_1serving_1_1SourceAdapter_a7c960f8493040fc8cb0766e4c2cebf60)
virtual method, which converts a servable version list from InputType to
OutputType.

IMPORTANT: Every leaf derived class must call Detach() at the top of its
destructor. (See documentation on TargetBase::Detach() in
[target.h](#target_8h_source).) Doing so ensures that no
[Adapt()](#classtensorflow_1_1serving_1_1SourceAdapter_a7c960f8493040fc8cb0766e4c2cebf60)
calls are in flight during destruction of member variables.

[\[classtensorflow\_1\_1serving\_1\_1SourceAdapter\_a7c960f8493040fc8cb0766e4c2cebf60\]]{#classtensorflow_1_1serving_1_1SourceAdapter_a7c960f8493040fc8cb0766e4c2cebf60
label="classtensorflow_1_1serving_1_1SourceAdapter_a7c960f8493040fc8cb0766e4c2cebf60"}

template$<$typename InputType , typename OutputType $>$\
virtual
std::vector$<$[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$OutputType$>$
$>$
[tensorflow::serving::SourceAdapter](#classtensorflow_1_1serving_1_1SourceAdapter)$<$
InputType, OutputType $>$::Adapt (

servable\_name,

versions

)

Given an InputType-based aspired-versions request, produces a
corresponding OutputType-based request.
[\[classtensorflow\_1\_1serving\_1\_1SourceAdapter\_a9775d0a39269efb319a0dbd94862f183\]]{#classtensorflow_1_1serving_1_1SourceAdapter_a9775d0a39269efb319a0dbd94862f183
label="classtensorflow_1_1serving_1_1SourceAdapter_a9775d0a39269efb319a0dbd94862f183"}

template$<$typename InputType , typename OutputType $>$\
void
[tensorflow::serving::SourceAdapter](#classtensorflow_1_1serving_1_1SourceAdapter)$<$
InputType, OutputType $>$::SetAspiredVersions (

servable\_name,

versions

),

This method is implemented in terms of
[Adapt()](#classtensorflow_1_1serving_1_1SourceAdapter_a7c960f8493040fc8cb0766e4c2cebf60),
which the implementing subclass must supply.

Implements
[tensorflow::serving::TargetBase$<$ InputType $>$](#classtensorflow_1_1serving_1_1TargetBase).

The documentation for this class was generated from the following file:

tensorflow\_serving/core/source\_adapter.h
