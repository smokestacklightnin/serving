::: {#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport}
:::

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerSupport\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport
label="classtensorflow_1_1serving_1_1net__http_1_1ServerSupport"}

Inheritance diagram for tensorflow::serving::net\_http::ServerSupport:

![image](classtensorflow_1_1serving_1_1net__http_1_1ServerSupport__inherit__graph.pdf){width="218pt"}

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerSupport\_a3d35ca48c4a55b6d0cfa3e7562c0c724\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_a3d35ca48c4a55b6d0cfa3e7562c0c724
label="classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_a3d35ca48c4a55b6d0cfa3e7562c0c724"}
**ServerSupport** (const
[ServerSupport](#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerSupport\_a31b3e2a5d39a83639a6818d9160ed9e9\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_a31b3e2a5d39a83639a6818d9160ed9e9
label="classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_a31b3e2a5d39a83639a6818d9160ed9e9"}
[ServerSupport](#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport)
& **operator=** (const
[ServerSupport](#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerSupport\_adc67e71e688ec87b02e4975366662572\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_adc67e71e688ec87b02e4975366662572
label="classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_adc67e71e688ec87b02e4975366662572"}
virtual void **IncOps** ()=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerSupport\_ac0f953ef4e30e321428aa564a38626c0\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_ac0f953ef4e30e321428aa564a38626c0
label="classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_ac0f953ef4e30e321428aa564a38626c0"}
virtual void **DecOps** ()=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ServerSupport\_ab71cd32f780088bfeaabc71c60f76ef8\]]{#classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_ab71cd32f780088bfeaabc71c60f76ef8
label="classtensorflow_1_1serving_1_1net__http_1_1ServerSupport_ab71cd32f780088bfeaabc71c60f76ef8"}
virtual bool **EventLoopSchedule** (std::function$<$ void()$>$ fn)=0

The documentation for this class was generated from the following file:

tensorflow\_serving/util/net\_http/server/internal/server\_support.h
