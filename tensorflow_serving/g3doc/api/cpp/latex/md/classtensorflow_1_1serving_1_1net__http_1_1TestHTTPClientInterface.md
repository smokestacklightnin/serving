::: {#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface}
:::

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestHTTPClientInterface\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface
label="classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface"}

Inheritance diagram for
tensorflow::serving::net\_http::TestHTTPClientInterface:

![image](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface__inherit__graph.pdf){width="261pt"}

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestHTTPClientInterface\_ae49eed1257f6090570e4fe8945a6e5f5\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_ae49eed1257f6090570e4fe8945a6e5f5
label="classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_ae49eed1257f6090570e4fe8945a6e5f5"}
**TestHTTPClientInterface** (const
[TestHTTPClientInterface](#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestHTTPClientInterface\_ab2475abd13f1dd54458ddcac63776314\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_ab2475abd13f1dd54458ddcac63776314
label="classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_ab2475abd13f1dd54458ddcac63776314"}
[TestHTTPClientInterface](#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface)
& **operator=** (const
[TestHTTPClientInterface](#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestHTTPClientInterface\_acde23c08ba3fdd8f505b3af232cb07f9\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_acde23c08ba3fdd8f505b3af232cb07f9
label="classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_acde23c08ba3fdd8f505b3af232cb07f9"}
virtual void **Terminate** ()=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestHTTPClientInterface\_af1e04d0a1089650328e351ea02a3ad1a\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_af1e04d0a1089650328e351ea02a3ad1a
label="classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_af1e04d0a1089650328e351ea02a3ad1a"}
virtual bool **BlockingSendRequest** (const
[TestClientRequest](#structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest)
&request,
[TestClientResponse](#structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse)
$\ast$response)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestHTTPClientInterface\_aafe1ccbaa3de907367ddae06c2f0259f\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_aafe1ccbaa3de907367ddae06c2f0259f
label="classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_aafe1ccbaa3de907367ddae06c2f0259f"}
virtual bool **SendRequest** (const
[TestClientRequest](#structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest)
&request,
[TestClientResponse](#structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse)
$\ast$response)=0

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1TestHTTPClientInterface\_a2e91cfa281e2ea32e891afc23aff62a8\]]{#classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_a2e91cfa281e2ea32e891afc23aff62a8
label="classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_a2e91cfa281e2ea32e891afc23aff62a8"}
virtual void **SetExecutor** (std::unique\_ptr$<$
[EventExecutor](#classtensorflow_1_1serving_1_1net__http_1_1EventExecutor)
$>$ executor)=0

The documentation for this class was generated from the following file:

tensorflow\_serving/util/net\_http/client/test\_client/public/httpclient\_interface.h
