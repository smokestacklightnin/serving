::: {#classtensorflow_1_1serving_1_1StaticSourceRouter}
:::

[\[classtensorflow\_1\_1serving\_1\_1StaticSourceRouter\]]{#classtensorflow_1_1serving_1_1StaticSourceRouter
label="classtensorflow_1_1serving_1_1StaticSourceRouter"}

Inheritance diagram for tensorflow::serving::StaticSourceRouter$<$ T
$>$:

![image](classtensorflow_1_1serving_1_1StaticSourceRouter__inherit__graph.pdf){width="224pt"}

Collaboration diagram for tensorflow::serving::StaticSourceRouter$<$ T
$>$:

![image](classtensorflow_1_1serving_1_1StaticSourceRouter__coll__graph.pdf){width="224pt"}

[\[classtensorflow\_1\_1serving\_1\_1StaticSourceRouter\_a647751391204afcda13a3a760e788ca8\]]{#classtensorflow_1_1serving_1_1StaticSourceRouter_a647751391204afcda13a3a760e788ca8
label="classtensorflow_1_1serving_1_1StaticSourceRouter_a647751391204afcda13a3a760e788ca8"}
static Status **Create** (const std::vector$<$ string $>$
&route\_substrings, std::unique\_ptr$<$
[StaticSourceRouter](#classtensorflow_1_1serving_1_1StaticSourceRouter)$<$
T $>$$>$ $\ast$result)

[\[classtensorflow\_1\_1serving\_1\_1StaticSourceRouter\_aff41319a0759646ceaca6bcb218f2bed\]]{#classtensorflow_1_1serving_1_1StaticSourceRouter_aff41319a0759646ceaca6bcb218f2bed
label="classtensorflow_1_1serving_1_1StaticSourceRouter_aff41319a0759646ceaca6bcb218f2bed"}
int **num\_output\_ports** () const override

[\[classtensorflow\_1\_1serving\_1\_1StaticSourceRouter\_a956a2d3e96e3c14a6cefbbd10eaca0d9\]]{#classtensorflow_1_1serving_1_1StaticSourceRouter_a956a2d3e96e3c14a6cefbbd10eaca0d9
label="classtensorflow_1_1serving_1_1StaticSourceRouter_a956a2d3e96e3c14a6cefbbd10eaca0d9"}
int **Route** (const StringPiece servable\_name, const std::vector$<$
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$ T $>$$>$
&versions) override

The documentation for this class was generated from the following file:

tensorflow\_serving/core/static\_source\_router.h
