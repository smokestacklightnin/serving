::: {#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options}
:::

[\[structtensorflow\_1\_1serving\_1\_1LoaderHarness\_1\_1Options\]]{#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options
label="structtensorflow_1_1serving_1_1LoaderHarness_1_1Options"}

[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options) to
configure a
[LoaderHarness](#classtensorflow_1_1serving_1_1LoaderHarness).

\#include $<$loader\_harness.h$>$

uint32
[max\_num\_load\_retries](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_a4774535a566aad29ab5bc0c7b3e0dc3e)
= 0

[\[structtensorflow\_1\_1serving\_1\_1LoaderHarness\_1\_1Options\_acbf10fe52eba4bee54882e25a62386e7\]]{#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_acbf10fe52eba4bee54882e25a62386e7
label="structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_acbf10fe52eba4bee54882e25a62386e7"}
uint64\_t
[load\_retry\_interval\_micros](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_acbf10fe52eba4bee54882e25a62386e7)
= 0

*The interval, in microseconds, between each servable load retry.*

[\[structtensorflow\_1\_1serving\_1\_1LoaderHarness\_1\_1Options\_a5f9d2107c294a1e6b0e9865ed9d34ec4\]]{#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_a5f9d2107c294a1e6b0e9865ed9d34ec4
label="structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_a5f9d2107c294a1e6b0e9865ed9d34ec4"}
std::function$<$ void(const
[ServableId](#structtensorflow_1_1serving_1_1ServableId)
&[id](#classtensorflow_1_1serving_1_1LoaderHarness_ac6581aa3aa10002465c0ffab0b83ab95),
const Status &error)$>$
[error\_callback](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_a5f9d2107c294a1e6b0e9865ed9d34ec4)

*An (optional) function to call upon transitioning to state kError.*

[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options) to
configure a
[LoaderHarness](#classtensorflow_1_1serving_1_1LoaderHarness).

[\[structtensorflow\_1\_1serving\_1\_1LoaderHarness\_1\_1Options\_a4774535a566aad29ab5bc0c7b3e0dc3e\]]{#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_a4774535a566aad29ab5bc0c7b3e0dc3e
label="structtensorflow_1_1serving_1_1LoaderHarness_1_1Options_a4774535a566aad29ab5bc0c7b3e0dc3e"}
uint32
tensorflow::serving::LoaderHarness::Options::max\_num\_load\_retries = 0

Maximum number of times we retry loading a servable, after the first
failure, before we give up.

The documentation for this struct was generated from the following file:

tensorflow\_serving/core/loader\_harness.h
