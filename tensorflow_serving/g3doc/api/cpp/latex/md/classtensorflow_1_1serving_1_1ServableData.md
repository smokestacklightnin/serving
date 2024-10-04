::: {#classtensorflow_1_1serving_1_1ServableData}
:::

[\[classtensorflow\_1\_1serving\_1\_1ServableData\]]{#classtensorflow_1_1serving_1_1ServableData
label="classtensorflow_1_1serving_1_1ServableData"}

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_a8d3b082862245d9f152d396f801b13b4\]]{#classtensorflow_1_1serving_1_1ServableData_a8d3b082862245d9f152d396f801b13b4
label="classtensorflow_1_1serving_1_1ServableData_a8d3b082862245d9f152d396f801b13b4"}
**ServableData** (const
[ServableId](#structtensorflow_1_1serving_1_1ServableId) &id, T data)

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_a052570c6f4bf50d0048783856d52a880\]]{#classtensorflow_1_1serving_1_1ServableData_a052570c6f4bf50d0048783856d52a880
label="classtensorflow_1_1serving_1_1ServableData_a052570c6f4bf50d0048783856d52a880"}
**ServableData** (const
[ServableId](#structtensorflow_1_1serving_1_1ServableId) &id, const
Status &error)

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_a2d32866ff899431fde41b55be1d68e7f\]]{#classtensorflow_1_1serving_1_1ServableData_a2d32866ff899431fde41b55be1d68e7f
label="classtensorflow_1_1serving_1_1ServableData_a2d32866ff899431fde41b55be1d68e7f"}
**ServableData** (const
[ServableData](#classtensorflow_1_1serving_1_1ServableData)
&other)=default

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_a5197e34455decd57af819f4930a03688\]]{#classtensorflow_1_1serving_1_1ServableData_a5197e34455decd57af819f4930a03688
label="classtensorflow_1_1serving_1_1ServableData_a5197e34455decd57af819f4930a03688"}
[ServableData](#classtensorflow_1_1serving_1_1ServableData) &
**operator=** (const
[ServableData](#classtensorflow_1_1serving_1_1ServableData)
&other)=default

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_ad816b45549d77bfe6f887f7c2696c75c\]]{#classtensorflow_1_1serving_1_1ServableData_ad816b45549d77bfe6f887f7c2696c75c
label="classtensorflow_1_1serving_1_1ServableData_ad816b45549d77bfe6f887f7c2696c75c"}
**ServableData**
([ServableData](#classtensorflow_1_1serving_1_1ServableData)
&&other)=default

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_a76ebe1f1b686b7e9c65bb6fe0d44394d\]]{#classtensorflow_1_1serving_1_1ServableData_a76ebe1f1b686b7e9c65bb6fe0d44394d
label="classtensorflow_1_1serving_1_1ServableData_a76ebe1f1b686b7e9c65bb6fe0d44394d"}
const [ServableId](#structtensorflow_1_1serving_1_1ServableId) & **id**
() const

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_a7d1a89d262d89fa0c15181b631ebade0\]]{#classtensorflow_1_1serving_1_1ServableData_a7d1a89d262d89fa0c15181b631ebade0
label="classtensorflow_1_1serving_1_1ServableData_a7d1a89d262d89fa0c15181b631ebade0"}
const Status & **status** () const

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_a828b4054a133b94d6aa9aa90060a5543\]]{#classtensorflow_1_1serving_1_1ServableData_a828b4054a133b94d6aa9aa90060a5543
label="classtensorflow_1_1serving_1_1ServableData_a828b4054a133b94d6aa9aa90060a5543"}
const T & **DataOrDie** () const

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_aa3d1d3968980a7c568917d9520127ff0\]]{#classtensorflow_1_1serving_1_1ServableData_aa3d1d3968980a7c568917d9520127ff0
label="classtensorflow_1_1serving_1_1ServableData_aa3d1d3968980a7c568917d9520127ff0"}
T & **DataOrDie** ()

[\[classtensorflow\_1\_1serving\_1\_1ServableData\_a4bc8255bbe2d6ef4f1d60bed15f9b8f6\]]{#classtensorflow_1_1serving_1_1ServableData_a4bc8255bbe2d6ef4f1d60bed15f9b8f6
label="classtensorflow_1_1serving_1_1ServableData_a4bc8255bbe2d6ef4f1d60bed15f9b8f6"}
T **ConsumeDataOrDie** ()

The documentation for this class was generated from the following file:

tensorflow\_serving/core/servable\_data.h
