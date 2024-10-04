::: {#classtensorflow_1_1serving_1_1SourceRouter}
:::

[\[classtensorflow\_1\_1serving\_1\_1SourceRouter\]]{#classtensorflow_1_1serving_1_1SourceRouter
label="classtensorflow_1_1serving_1_1SourceRouter"}

Inheritance diagram for tensorflow::serving::SourceRouter$<$ T $>$:

![image](classtensorflow_1_1serving_1_1SourceRouter__inherit__graph.pdf){width="350pt"}

Collaboration diagram for tensorflow::serving::SourceRouter$<$ T $>$:

![image](classtensorflow_1_1serving_1_1SourceRouter__coll__graph.pdf){width="196pt"}

[\[classtensorflow\_1\_1serving\_1\_1SourceRouter\_a41707304d32cec4cdb7b9f65c81663e7\]]{#classtensorflow_1_1serving_1_1SourceRouter_a41707304d32cec4cdb7b9f65c81663e7
label="classtensorflow_1_1serving_1_1SourceRouter_a41707304d32cec4cdb7b9f65c81663e7"}
std::vector$<$ [Source](#classtensorflow_1_1serving_1_1Source)$<$ T $>$
$\ast$ $>$ **GetOutputPorts** ()

[\[classtensorflow\_1\_1serving\_1\_1SourceRouter\_abc1d76cecc39499969776118ea3a8eb8\]]{#classtensorflow_1_1serving_1_1SourceRouter_abc1d76cecc39499969776118ea3a8eb8
label="classtensorflow_1_1serving_1_1SourceRouter_abc1d76cecc39499969776118ea3a8eb8"}
void **SetAspiredVersions** (const StringPiece servable\_name,
std::vector$<$
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$ T $>$$>$
versions) final

[\[classtensorflow\_1\_1serving\_1\_1SourceRouter\_a1634ab37e95479ab4a095843b0419925\]]{#classtensorflow_1_1serving_1_1SourceRouter_a1634ab37e95479ab4a095843b0419925
label="classtensorflow_1_1serving_1_1SourceRouter_a1634ab37e95479ab4a095843b0419925"}
static constexpr int **kNoRoute** = -1

[\[classtensorflow\_1\_1serving\_1\_1SourceRouter\_ae44476828b7d7d17a1dfe182828b604e\]]{#classtensorflow_1_1serving_1_1SourceRouter_ae44476828b7d7d17a1dfe182828b604e
label="classtensorflow_1_1serving_1_1SourceRouter_ae44476828b7d7d17a1dfe182828b604e"}
virtual int **num\_output\_ports** () const =0

[\[classtensorflow\_1\_1serving\_1\_1SourceRouter\_a3d6240ed0e9aa13fac153d7fbf76c2d1\]]{#classtensorflow_1_1serving_1_1SourceRouter_a3d6240ed0e9aa13fac153d7fbf76c2d1
label="classtensorflow_1_1serving_1_1SourceRouter_a3d6240ed0e9aa13fac153d7fbf76c2d1"}
virtual int **Route** (const StringPiece servable\_name, const
std::vector$<$
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$ T $>$$>$
&versions)=0

The documentation for this class was generated from the following file:

tensorflow\_serving/core/source\_router.h
