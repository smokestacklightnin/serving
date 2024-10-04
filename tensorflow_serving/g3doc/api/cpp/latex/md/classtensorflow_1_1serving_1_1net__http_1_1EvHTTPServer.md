::: {#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer}
:::

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer"}

Inheritance diagram for tensorflow::serving::net\_http::EvHTTPServer:

![image](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer__inherit__graph.pdf){width="350pt"}

Collaboration diagram for tensorflow::serving::net\_http::EvHTTPServer:

![image](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer__coll__graph.pdf){width="350pt"}

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_aa1b6616f36c1cda4f8e90574711e4e31\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_aa1b6616f36c1cda4f8e90574711e4e31
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_aa1b6616f36c1cda4f8e90574711e4e31"}
**EvHTTPServer** (const
[EvHTTPServer](#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_a2fcbe7012275a5edf9887b3318c6388e\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a2fcbe7012275a5edf9887b3318c6388e
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a2fcbe7012275a5edf9887b3318c6388e"}
[EvHTTPServer](#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer)
& **operator=** (const
[EvHTTPServer](#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_af5c8692434e8b849ef39d34a19b0c059\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_af5c8692434e8b849ef39d34a19b0c059
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_af5c8692434e8b849ef39d34a19b0c059"}
**EvHTTPServer** (std::unique\_ptr$<$
[ServerOptions](#classtensorflow_1_1serving_1_1net__http_1_1ServerOptions)
$>$ options)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_a7023abbfb04afcc506be3bde08b9c063\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a7023abbfb04afcc506be3bde08b9c063
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a7023abbfb04afcc506be3bde08b9c063"}
bool **Initialize** ()

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_ac2e62ff79c6e61374c3a7d4bec8a184a\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_ac2e62ff79c6e61374c3a7d4bec8a184a
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_ac2e62ff79c6e61374c3a7d4bec8a184a"}
bool **StartAcceptingRequests** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_ac15faca9bccd2429aed0c8fe4672d9bd\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_ac15faca9bccd2429aed0c8fe4672d9bd
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_ac15faca9bccd2429aed0c8fe4672d9bd"}
bool **is\_accepting\_requests** () const override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_a8b686f94f4c0a6e6b3ab6bf290b501a7\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a8b686f94f4c0a6e6b3ab6bf290b501a7
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a8b686f94f4c0a6e6b3ab6bf290b501a7"}
int **listen\_port** () const override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_aa996becd4828ac4b25de40ba14085b80\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_aa996becd4828ac4b25de40ba14085b80
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_aa996becd4828ac4b25de40ba14085b80"}
void **Terminate** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_a63ae433a02cc051b3dfb4f581cae9140\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a63ae433a02cc051b3dfb4f581cae9140
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a63ae433a02cc051b3dfb4f581cae9140"}
bool **is\_terminating** () const override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_a6c1f5464b86b5c15b99eb9b202f7102f\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a6c1f5464b86b5c15b99eb9b202f7102f
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a6c1f5464b86b5c15b99eb9b202f7102f"}
void **WaitForTermination** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_afd252461c5e8a327f63788f9f22856d9\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_afd252461c5e8a327f63788f9f22856d9
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_afd252461c5e8a327f63788f9f22856d9"}
bool **WaitForTerminationWithTimeout** (absl::Duration timeout) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_aadda38e432cb6b454e896ed6dcea8299\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_aadda38e432cb6b454e896ed6dcea8299
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_aadda38e432cb6b454e896ed6dcea8299"}
void **RegisterRequestHandler** (absl::string\_view uri, RequestHandler
handler, const
[RequestHandlerOptions](#classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions)
&options) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_ac1037d34b1cc20d188c00915ced82327\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_ac1037d34b1cc20d188c00915ced82327
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_ac1037d34b1cc20d188c00915ced82327"}
void **RegisterRequestDispatcher** (RequestDispatcher dispatcher, const
[RequestHandlerOptions](#classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions)
&options) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_a81512ffd0c51361eab22e2aa1f981a9e\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a81512ffd0c51361eab22e2aa1f981a9e
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a81512ffd0c51361eab22e2aa1f981a9e"}
void **IncOps** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_a7130ccc1f427b117b4749a4eac69150d\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a7130ccc1f427b117b4749a4eac69150d
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_a7130ccc1f427b117b4749a4eac69150d"}
void **DecOps** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1EvHTTPServer\_ab9d18f5adb974f21d79b45441c6bcc7d\]]{#classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_ab9d18f5adb974f21d79b45441c6bcc7d
label="classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_ab9d18f5adb974f21d79b45441c6bcc7d"}
bool **EventLoopSchedule** (std::function$<$ void()$>$ fn) override

The documentation for this class was generated from the following files:

tensorflow\_serving/util/net\_http/server/internal/evhttp\_server.h

tensorflow\_serving/util/net\_http/server/internal/evhttp\_server.cc
