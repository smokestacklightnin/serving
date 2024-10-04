::: {#classtensorflow_1_1serving_1_1FileProbingEnv}
:::

[\[classtensorflow\_1\_1serving\_1\_1FileProbingEnv\]]{#classtensorflow_1_1serving_1_1FileProbingEnv
label="classtensorflow_1_1serving_1_1FileProbingEnv"}

Inheritance diagram for tensorflow::serving::FileProbingEnv:

![image](classtensorflow_1_1serving_1_1FileProbingEnv__inherit__graph.pdf){width="350pt"}

[\[classtensorflow\_1\_1serving\_1\_1FileProbingEnv\_a933f76b27dba3a066bee6a45813f2f6d\]]{#classtensorflow_1_1serving_1_1FileProbingEnv_a933f76b27dba3a066bee6a45813f2f6d
label="classtensorflow_1_1serving_1_1FileProbingEnv_a933f76b27dba3a066bee6a45813f2f6d"}
virtual Status **FileExists** (const string &fname)=0

[\[classtensorflow\_1\_1serving\_1\_1FileProbingEnv\_ae89f287e23c96b691444b8c0309a3b2c\]]{#classtensorflow_1_1serving_1_1FileProbingEnv_ae89f287e23c96b691444b8c0309a3b2c
label="classtensorflow_1_1serving_1_1FileProbingEnv_ae89f287e23c96b691444b8c0309a3b2c"}
virtual Status **GetChildren** (const string &dir, std::vector$<$ string
$>$ $\ast$children)=0

[\[classtensorflow\_1\_1serving\_1\_1FileProbingEnv\_acaaeab37af993bbb0044a0821eca77ff\]]{#classtensorflow_1_1serving_1_1FileProbingEnv_acaaeab37af993bbb0044a0821eca77ff
label="classtensorflow_1_1serving_1_1FileProbingEnv_acaaeab37af993bbb0044a0821eca77ff"}
virtual Status **IsDirectory** (const string &fname)=0

[\[classtensorflow\_1\_1serving\_1\_1FileProbingEnv\_aa3a8674f3f0dfc3db90bafb7107df2e6\]]{#classtensorflow_1_1serving_1_1FileProbingEnv_aa3a8674f3f0dfc3db90bafb7107df2e6
label="classtensorflow_1_1serving_1_1FileProbingEnv_aa3a8674f3f0dfc3db90bafb7107df2e6"}
virtual Status **GetFileSize** (const string &fname, uint64\_t
$\ast$file\_size)=0

The documentation for this class was generated from the following file:

tensorflow\_serving/util/file\_probing\_env.h
