::: {#classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs}
:::

[\[classtensorflow\_1\_1serving\_1\_1internal\_\_read\_\_ptr\_\_holder\_1\_1ShardedReadPtrs\]]{#classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs
label="classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs"}

[\[classtensorflow\_1\_1serving\_1\_1internal\_\_read\_\_ptr\_\_holder\_1\_1ShardedReadPtrs\_a8541a397c711d897de99839e8c5c038e\]]{#classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_a8541a397c711d897de99839e8c5c038e
label="classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_a8541a397c711d897de99839e8c5c038e"}
std::shared\_ptr$<$ const T $>$ **get** () const

[\[classtensorflow\_1\_1serving\_1\_1internal\_\_read\_\_ptr\_\_holder\_1\_1ShardedReadPtrs\_a335097c3ce42909cb3fdb2cc7f85861d\]]{#classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_a335097c3ce42909cb3fdb2cc7f85861d
label="classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_a335097c3ce42909cb3fdb2cc7f85861d"}
template$<$typename Factory $>$ \
void **update** (const Factory &f)

const int **num\_shards\_**

[\[classtensorflow\_1\_1serving\_1\_1internal\_\_read\_\_ptr\_\_holder\_1\_1ShardedReadPtrs\_a10fe2301a7efb679c7f3d8561595575b\]]{#classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_a10fe2301a7efb679c7f3d8561595575b
label="classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_a10fe2301a7efb679c7f3d8561595575b"}
std::atomic$<$ uint32 $>$ **index\_** {0}

[\[classtensorflow\_1\_1serving\_1\_1internal\_\_read\_\_ptr\_\_holder\_1\_1ShardedReadPtrs\_ade80b9211220c2b6e414ae4541632902\]]{#classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_ade80b9211220c2b6e414ae4541632902
label="classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_ade80b9211220c2b6e414ae4541632902"}
std::unique\_ptr$<$ PaddedThreadSafeSharedPtr\[$\,$\]$>$ **shards\_**

[\[classtensorflow\_1\_1serving\_1\_1internal\_\_read\_\_ptr\_\_holder\_1\_1ShardedReadPtrs\_a0f614fbd78619b91a8621e393a3a43f7\]]{#classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_a0f614fbd78619b91a8621e393a3a43f7
label="classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_a0f614fbd78619b91a8621e393a3a43f7"}
template$<$typename T $>$\
const int
[tensorflow::serving::internal\_read\_ptr\_holder::ShardedReadPtrs](#classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs)$<$
T $>$::num\_shards\_

**Initial value:**

0

The documentation for this class was generated from the following file:

tensorflow\_serving/util/fast\_read\_dynamic\_ptr.h
