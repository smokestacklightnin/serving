::: {#classtensorflow_1_1serving_1_1LogCollector}
:::

[\[classtensorflow\_1\_1serving\_1\_1LogCollector\]]{#classtensorflow_1_1serving_1_1LogCollector
label="classtensorflow_1_1serving_1_1LogCollector"}

Inheritance diagram for tensorflow::serving::LogCollector:

![image](classtensorflow_1_1serving_1_1LogCollector__inherit__graph.pdf){width="318pt"}

[\[classtensorflow\_1\_1serving\_1\_1LogCollector\_abb47f70e33f17c5c987956aa4cab1d7d\]]{#classtensorflow_1_1serving_1_1LogCollector_abb47f70e33f17c5c987956aa4cab1d7d
label="classtensorflow_1_1serving_1_1LogCollector_abb47f70e33f17c5c987956aa4cab1d7d"}
using **Factory** = std::function$<$ decltype(Create)$>$

[\[classtensorflow\_1\_1serving\_1\_1LogCollector\_a48c04c9fa62d00442deebdeb65ba5dd0\]]{#classtensorflow_1_1serving_1_1LogCollector_a48c04c9fa62d00442deebdeb65ba5dd0
label="classtensorflow_1_1serving_1_1LogCollector_a48c04c9fa62d00442deebdeb65ba5dd0"}
virtual Status **CollectMessage** (const google::protobuf::Message
&message)=0

[\[classtensorflow\_1\_1serving\_1\_1LogCollector\_a7d2af55f5821f931643ca0f613ec50a7\]]{#classtensorflow_1_1serving_1_1LogCollector_a7d2af55f5821f931643ca0f613ec50a7
label="classtensorflow_1_1serving_1_1LogCollector_a7d2af55f5821f931643ca0f613ec50a7"}
virtual Status **Flush** ()=0

[\[classtensorflow\_1\_1serving\_1\_1LogCollector\_aeed35b69eca1e5e70f69f56b9432a92c\]]{#classtensorflow_1_1serving_1_1LogCollector_aeed35b69eca1e5e70f69f56b9432a92c
label="classtensorflow_1_1serving_1_1LogCollector_aeed35b69eca1e5e70f69f56b9432a92c"}
static Status **Create** (const LogCollectorConfig
&log\_collector\_config, const uint32 id, std::unique\_ptr$<$
[LogCollector](#classtensorflow_1_1serving_1_1LogCollector) $>$
$\ast$log\_collector)

[\[classtensorflow\_1\_1serving\_1\_1LogCollector\_a01ec37a4efb29a70ce7a70f2c35a19f7\]]{#classtensorflow_1_1serving_1_1LogCollector_a01ec37a4efb29a70ce7a70f2c35a19f7
label="classtensorflow_1_1serving_1_1LogCollector_a01ec37a4efb29a70ce7a70f2c35a19f7"}
static Status **RegisterFactory** (const string &type, const Factory
&factory)

The documentation for this class was generated from the following files:

tensorflow\_serving/core/log\_collector.h

tensorflow\_serving/core/log\_collector.cc
