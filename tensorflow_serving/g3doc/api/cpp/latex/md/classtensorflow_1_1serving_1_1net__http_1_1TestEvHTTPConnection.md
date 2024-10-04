::: {#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection}
:::

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection"}

Inheritance diagram for
tensorflow::serving::net\_http::TestEvHTTPConnection:

![image](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection__inherit__graph.pdf){width="261pt"}

Collaboration diagram for
tensorflow::serving::net\_http::TestEvHTTPConnection:

![image](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection__coll__graph.pdf){width="261pt"}

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_af0f6d1a44ae8cde23369bbf67e0a64d8\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_af0f6d1a44ae8cde23369bbf67e0a64d8
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_af0f6d1a44ae8cde23369bbf67e0a64d8"}
**TestEvHTTPConnection** (const
[TestEvHTTPConnection](#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_aaa3298c849c68d9b4d54cea31493a72b\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_aaa3298c849c68d9b4d54cea31493a72b
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_aaa3298c849c68d9b4d54cea31493a72b"}
[TestEvHTTPConnection](#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection)
& **operator=** (const
[TestEvHTTPConnection](#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_aa6514c0457bcf28c33f9bc074a4d2833\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_aa6514c0457bcf28c33f9bc074a4d2833
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_aa6514c0457bcf28c33f9bc074a4d2833"}
void **Terminate** () override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_a8fd460b64308127e543562b78652f080\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a8fd460b64308127e543562b78652f080
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a8fd460b64308127e543562b78652f080"}
bool **BlockingSendRequest** (const
[TestClientRequest](#structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest)
&request,
[TestClientResponse](#structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse)
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_a41357800736a2bc4516cb18b9eb4e55e\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a41357800736a2bc4516cb18b9eb4e55e
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a41357800736a2bc4516cb18b9eb4e55e"}
bool **SendRequest** (const
[TestClientRequest](#structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest)
&request,
[TestClientResponse](#structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse)
$\ast$response) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_a117a8f7ddc785ee7832a8a366ef5cc6c\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a117a8f7ddc785ee7832a8a366ef5cc6c
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a117a8f7ddc785ee7832a8a366ef5cc6c"}
void **SetExecutor** (std::unique\_ptr$<$
[EventExecutor](#classtensorflow_1_1serving_1_1net__http_1_1EventExecutor)
$>$ executor) override

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_a474285be99fdd4cf595f91da3fbc729e\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a474285be99fdd4cf595f91da3fbc729e
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a474285be99fdd4cf595f91da3fbc729e"}
static std::unique\_ptr$<$
[TestEvHTTPConnection](#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection)
$>$ **Connect** (absl::string\_view url)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_a2710dfe62103f842758ded371631214b\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a2710dfe62103f842758ded371631214b
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a2710dfe62103f842758ded371631214b"}
static std::unique\_ptr$<$
[TestEvHTTPConnection](#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection)
$>$ **Connect** (absl::string\_view host, int port)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestEvHTTPConnection\_a81445984f79a709567d7981d05d7a347\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a81445984f79a709567d7981d05d7a347
label="classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_a81445984f79a709567d7981d05d7a347"}
static std::unique\_ptr$<$
[TestEvHTTPConnection](#classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection)
$>$ **ConnectLocal** (int port)

The documentation for this class was generated from the following files:

tensorflow\_serving/util/net\_http/client/test\_client/internal/evhttp\_connection.h

tensorflow\_serving/util/net\_http/client/test\_client/internal/evhttp\_connection.cc
