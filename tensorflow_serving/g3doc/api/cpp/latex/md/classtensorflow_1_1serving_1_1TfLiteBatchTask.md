::: {#classtensorflow_1_1serving_1_1TfLiteBatchTask}
:::

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask
label="classtensorflow_1_1serving_1_1TfLiteBatchTask"}

Inheritance diagram for tensorflow::serving::TfLiteBatchTask:

![image](classtensorflow_1_1serving_1_1TfLiteBatchTask__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::TfLiteBatchTask:

![image](classtensorflow_1_1serving_1_1TfLiteBatchTask__coll__graph.pdf){width="339pt"}

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a5c05ffc8dd54733018497b1965c13f46\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a5c05ffc8dd54733018497b1965c13f46
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a5c05ffc8dd54733018497b1965c13f46"}
**TfLiteBatchTask** (const
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask)
&)=delete

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_ade9a671fa58f2fa82de3f208029804ae\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_ade9a671fa58f2fa82de3f208029804ae
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_ade9a671fa58f2fa82de3f208029804ae"}
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask) &
**operator=** (const
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask)
&)=delete

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a37ffa33cc0dcf6216be76c83da19055c\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a37ffa33cc0dcf6216be76c83da19055c
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a37ffa33cc0dcf6216be76c83da19055c"}
size\_t **size** () const override

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a43c0d58bae5a72ef4aad11362edc51af\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a43c0d58bae5a72ef4aad11362edc51af
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a43c0d58bae5a72ef4aad11362edc51af"}
uint64\_t **start\_time\_micros** () const

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_af192631ca3f7084a58145c15d90ce68d\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_af192631ca3f7084a58145c15d90ce68d
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_af192631ca3f7084a58145c15d90ce68d"}
void **set\_output** (Tensor t)

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_af0672c8f2c6e5c9582b5b01e34233211\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_af0672c8f2c6e5c9582b5b01e34233211
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_af0672c8f2c6e5c9582b5b01e34233211"}
static void **CreateTfLiteBatchTask** (const std::vector$<$ string $>$
$\ast$output\_tensor\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
Notification $\ast$done, Status $\ast$status, std::unique\_ptr$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask) $>$
$\ast$batch\_task)

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a94a8eb3acbe6a6a5a144ff837addcb05\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a94a8eb3acbe6a6a5a144ff837addcb05
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a94a8eb3acbe6a6a5a144ff837addcb05"}
static void **CreatePartialTfLiteBatchTask** (std::vector$<$ int $>$
input\_indices, const std::vector$<$ string $>$
$\ast$output\_tensor\_names, std::vector$<$ Tensor $>$ $\ast$outputs,
std::function$<$ void()$>$ done\_callback,
[ThreadSafeStatus](#classtensorflow_1_1serving_1_1ThreadSafeStatus)
$\ast$partial\_status, std::unique\_ptr$<$
[TfLiteBatchTask](#classtensorflow_1_1serving_1_1TfLiteBatchTask) $>$
$\ast$batch\_task)

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_aefce7b4a3a1ecaea9b422741c2f6e15c\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_aefce7b4a3a1ecaea9b422741c2f6e15c
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_aefce7b4a3a1ecaea9b422741c2f6e15c"}
Notification $\ast$ **done**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a81366e876a3da7d8b95a266c2e75c6d5\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a81366e876a3da7d8b95a266c2e75c6d5
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a81366e876a3da7d8b95a266c2e75c6d5"}
Status $\ast$ **status**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_ac2ac92f1dced5f3d6517a32cc10799c6\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_ac2ac92f1dced5f3d6517a32cc10799c6
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_ac2ac92f1dced5f3d6517a32cc10799c6"}
std::vector$<$ int $>$ **input\_indices**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a39139f7e669295fe997044990a368b2f\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a39139f7e669295fe997044990a368b2f
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a39139f7e669295fe997044990a368b2f"}
std::vector$<$ Tensor $>$ **inputs**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a41b9581c0fc4f3d9dcfed55725a7d500\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a41b9581c0fc4f3d9dcfed55725a7d500
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a41b9581c0fc4f3d9dcfed55725a7d500"}
std::vector$<$ Tensor $>$ $\ast$ **outputs**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a4e9337745fcae421a2f19ef45bb9922d\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a4e9337745fcae421a2f19ef45bb9922d
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a4e9337745fcae421a2f19ef45bb9922d"}
const std::vector$<$ string $>$ $\ast$ **output\_tensor\_names**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a05ba18525cef1551e7c18c89ea5f995e\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a05ba18525cef1551e7c18c89ea5f995e
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a05ba18525cef1551e7c18c89ea5f995e"}
RunOptions **run\_options**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_aab7b91875799bf556987b67ace4fedd8\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_aab7b91875799bf556987b67ace4fedd8
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_aab7b91875799bf556987b67ace4fedd8"}
const uint64\_t **enqueue\_time\_micros**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a114b29e1b5806783a6cf511ba115e969\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a114b29e1b5806783a6cf511ba115e969
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a114b29e1b5806783a6cf511ba115e969"}
bool **is\_partial** = false

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a71ff12e665f405d20fb1c56dec47b483\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a71ff12e665f405d20fb1c56dec47b483
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a71ff12e665f405d20fb1c56dec47b483"}
std::function$<$ void()$>$ **done\_callback**

[\[classtensorflow\_1\_1serving\_1\_1TfLiteBatchTask\_a2f16ac86a5a9d7f9b013223664d5ea76\]]{#classtensorflow_1_1serving_1_1TfLiteBatchTask_a2f16ac86a5a9d7f9b013223664d5ea76
label="classtensorflow_1_1serving_1_1TfLiteBatchTask_a2f16ac86a5a9d7f9b013223664d5ea76"}
[ThreadSafeStatus](#classtensorflow_1_1serving_1_1ThreadSafeStatus)
$\ast$ **partial\_status**

The documentation for this class was generated from the following file:

tensorflow\_serving/servables/tensorflow/tflite\_session.h
