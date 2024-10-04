::: {#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest"}

Inheritance diagram for
tensorflow::serving::test\_util::BundleFactoryTest:

![image](classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest__inherit__graph.pdf){width="237pt"}

Collaboration diagram for
tensorflow::serving::test\_util::BundleFactoryTest:

![image](classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest__coll__graph.pdf){width="237pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\_a1a8d62a4d3f83c842cbab480a16ba0cf\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a1a8d62a4d3f83c842cbab480a16ba0cf
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a1a8d62a4d3f83c842cbab480a16ba0cf"}
**BundleFactoryTest** (const string &export\_dir)

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\_aa2466649dd92113af9a740e14cb02edf\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_aa2466649dd92113af9a740e14cb02edf
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_aa2466649dd92113af9a740e14cb02edf"}
void **TestBasic** () const

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\_a2084208191650d492311b9bac8129273\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a2084208191650d492311b9bac8129273
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a2084208191650d492311b9bac8129273"}
int **GetTotalBatchesProcessed** () const

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\_a0885bbf7ec02d880bc4a67e75eff1aba\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a0885bbf7ec02d880bc4a67e75eff1aba
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a0885bbf7ec02d880bc4a67e75eff1aba"}
void **TestBatching** (const BatchingParameters &params, bool
enable\_per\_model\_batching\_params, int input\_request\_batch\_size,
int batch\_size) const

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\_a77c7e2e244d0e70bc537bd72a771fd41\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a77c7e2e244d0e70bc537bd72a771fd41
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a77c7e2e244d0e70bc537bd72a771fd41"}
template$<$class FactoryType $>$ \
void **TestEstimateResourceRequirementWithGoodExport** (double
total\_file\_size) const

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\_ab951b925d2cf2ce9299682c989bae769\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_ab951b925d2cf2ce9299682c989bae769
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_ab951b925d2cf2ce9299682c989bae769"}
void **TestRunOptions** () const

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\_a10afbcc52b0b6cb015cc1de9b38cc3c2\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a10afbcc52b0b6cb015cc1de9b38cc3c2
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a10afbcc52b0b6cb015cc1de9b38cc3c2"}
void **TestRunOptionsError** () const

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1BundleFactoryTest\_a64ad8fa2075bdcc17df8f21888758cbd\]]{#classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a64ad8fa2075bdcc17df8f21888758cbd
label="classtensorflow_1_1serving_1_1test__util_1_1BundleFactoryTest_a64ad8fa2075bdcc17df8f21888758cbd"}
string **export\_dir\_**

The documentation for this class was generated from the following file:

tensorflow\_serving/servables/tensorflow/bundle\_factory\_test.h
