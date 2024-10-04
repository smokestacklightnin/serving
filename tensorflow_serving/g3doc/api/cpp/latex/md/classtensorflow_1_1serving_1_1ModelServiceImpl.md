::: {#classtensorflow_1_1serving_1_1ModelServiceImpl}
:::

[\[classtensorflow\_1\_1serving\_1\_1ModelServiceImpl\]]{#classtensorflow_1_1serving_1_1ModelServiceImpl
label="classtensorflow_1_1serving_1_1ModelServiceImpl"}

Inheritance diagram for tensorflow::serving::ModelServiceImpl:

![image](classtensorflow_1_1serving_1_1ModelServiceImpl__inherit__graph.pdf){width="205pt"}

Collaboration diagram for tensorflow::serving::ModelServiceImpl:

![image](classtensorflow_1_1serving_1_1ModelServiceImpl__coll__graph.pdf){width="205pt"}

[\[classtensorflow\_1\_1serving\_1\_1ModelServiceImpl\_adef4184f526b59c61ea034ab4232956a\]]{#classtensorflow_1_1serving_1_1ModelServiceImpl_adef4184f526b59c61ea034ab4232956a
label="classtensorflow_1_1serving_1_1ModelServiceImpl_adef4184f526b59c61ea034ab4232956a"}
**ModelServiceImpl**
([ServerCore](#classtensorflow_1_1serving_1_1ServerCore) $\ast$core)

[\[classtensorflow\_1\_1serving\_1\_1ModelServiceImpl\_a0953cc5dacce0b9e9197a20a7c4a3415\]]{#classtensorflow_1_1serving_1_1ModelServiceImpl_a0953cc5dacce0b9e9197a20a7c4a3415
label="classtensorflow_1_1serving_1_1ModelServiceImpl_a0953cc5dacce0b9e9197a20a7c4a3415"}
::grpc::Status **GetModelStatus** (::grpc::ServerContext $\ast$context,
const GetModelStatusRequest $\ast$request, GetModelStatusResponse
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1ModelServiceImpl\_a170dc36a49d334c2f2d4b209826c3711\]]{#classtensorflow_1_1serving_1_1ModelServiceImpl_a170dc36a49d334c2f2d4b209826c3711
label="classtensorflow_1_1serving_1_1ModelServiceImpl_a170dc36a49d334c2f2d4b209826c3711"}
::grpc::Status **HandleReloadConfigRequest** (::grpc::ServerContext
$\ast$context, const ReloadConfigRequest $\ast$request,
ReloadConfigResponse $\ast$response)

The documentation for this class was generated from the following files:

tensorflow\_serving/model\_servers/model\_service\_impl.h

tensorflow\_serving/model\_servers/model\_service\_impl.cc
