::: {#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface}
:::

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface"}

Inheritance diagram for
tensorflow::serving::net\_http::HTTPServerInterface:

![image](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface__inherit__graph.pdf){width="250pt"}

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_a4f1cf1db0053a0b0eab8bd85f81352f8\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a4f1cf1db0053a0b0eab8bd85f81352f8
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a4f1cf1db0053a0b0eab8bd85f81352f8"}
**HTTPServerInterface** (const
[HTTPServerInterface](#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_a700533fbe8566d71891dcb2d58a5f947\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a700533fbe8566d71891dcb2d58a5f947
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a700533fbe8566d71891dcb2d58a5f947"}
[HTTPServerInterface](#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface)
& **operator=** (const
[HTTPServerInterface](#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_aa9d6351af089d1bab5fc35773a2e25a4\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_aa9d6351af089d1bab5fc35773a2e25a4
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_aa9d6351af089d1bab5fc35773a2e25a4"}
virtual bool **StartAcceptingRequests** ()=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_acc37ed0b05e45acb5686b8a542aa4690\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_acc37ed0b05e45acb5686b8a542aa4690
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_acc37ed0b05e45acb5686b8a542aa4690"}
virtual bool **is\_accepting\_requests** () const =0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_a6d53c691cb283b9e35009ef78bd59557\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a6d53c691cb283b9e35009ef78bd59557
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a6d53c691cb283b9e35009ef78bd59557"}
virtual int **listen\_port** () const =0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_a4df01bf3ae378e0110a8a195f5685b58\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a4df01bf3ae378e0110a8a195f5685b58
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a4df01bf3ae378e0110a8a195f5685b58"}
virtual void **Terminate** ()=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_a39a43fb61bacc71eca05577d3a80e06e\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a39a43fb61bacc71eca05577d3a80e06e
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a39a43fb61bacc71eca05577d3a80e06e"}
virtual bool **is\_terminating** () const =0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_ae456dc3a021155c699b3c04b7aa14671\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_ae456dc3a021155c699b3c04b7aa14671
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_ae456dc3a021155c699b3c04b7aa14671"}
virtual void **WaitForTermination** ()=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_ae42b77ffc71e6b06d2ecdc64540b20d5\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_ae42b77ffc71e6b06d2ecdc64540b20d5
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_ae42b77ffc71e6b06d2ecdc64540b20d5"}
virtual bool **WaitForTerminationWithTimeout** (absl::Duration
timeout)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_aaa01a4d98cf452999b723b0f91b53fe3\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_aaa01a4d98cf452999b723b0f91b53fe3
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_aaa01a4d98cf452999b723b0f91b53fe3"}
virtual void **RegisterRequestHandler** (absl::string\_view uri,
RequestHandler handler, const
[RequestHandlerOptions](#classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions)
&options)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1HTTPServerInterface\_a0b7282560b2c39fbcca8b717b3e96122\]]{#classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a0b7282560b2c39fbcca8b717b3e96122
label="classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_a0b7282560b2c39fbcca8b717b3e96122"}
virtual void **RegisterRequestDispatcher** (RequestDispatcher
dispatcher, const
[RequestHandlerOptions](#classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions)
&options)=0

The documentation for this class was generated from the following file:

tensorflow\_serving/util/net\_http/server/public/httpserver\_interface.h
