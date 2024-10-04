::: {#classtensorflow_1_1serving_1_1FileSystemStoragePathSource}
:::

[\[classtensorflow\_1\_1serving\_1\_1FileSystemStoragePathSource\]]{#classtensorflow_1_1serving_1_1FileSystemStoragePathSource
label="classtensorflow_1_1serving_1_1FileSystemStoragePathSource"}

\#include $<$file\_system\_storage\_path\_source.h$>$

Inheritance diagram for
tensorflow::serving::FileSystemStoragePathSource:

![image](classtensorflow_1_1serving_1_1FileSystemStoragePathSource__inherit__graph.pdf){width="248pt"}

Collaboration diagram for
tensorflow::serving::FileSystemStoragePathSource:

![image](classtensorflow_1_1serving_1_1FileSystemStoragePathSource__coll__graph.pdf){width="248pt"}

Status
[UpdateConfig](#classtensorflow_1_1serving_1_1FileSystemStoragePathSource_ad29df4b1d9628b03723474db5a0d6ad0)
(const FileSystemStoragePathSourceConfig &config)

[\[classtensorflow\_1\_1serving\_1\_1FileSystemStoragePathSource\_a3f341338d7fe9be5176eb788222df5b0\]]{#classtensorflow_1_1serving_1_1FileSystemStoragePathSource_a3f341338d7fe9be5176eb788222df5b0
label="classtensorflow_1_1serving_1_1FileSystemStoragePathSource_a3f341338d7fe9be5176eb788222df5b0"}
void **SetAspiredVersionsCallback**
([AspiredVersionsCallback](#classtensorflow_1_1serving_1_1Source_aeb281087e1478b0ff4a74e3f60496c6f)
callback) override

[\[classtensorflow\_1\_1serving\_1\_1FileSystemStoragePathSource\_a8ee923530b9479c220996691a06c464a\]]{#classtensorflow_1_1serving_1_1FileSystemStoragePathSource_a8ee923530b9479c220996691a06c464a
label="classtensorflow_1_1serving_1_1FileSystemStoragePathSource_a8ee923530b9479c220996691a06c464a"}
FileSystemStoragePathSourceConfig **config** () const

[\[classtensorflow\_1\_1serving\_1\_1FileSystemStoragePathSource\_a9f8e64bda0d205fd9bb34bf54f18857c\]]{#classtensorflow_1_1serving_1_1FileSystemStoragePathSource_a9f8e64bda0d205fd9bb34bf54f18857c
label="classtensorflow_1_1serving_1_1FileSystemStoragePathSource_a9f8e64bda0d205fd9bb34bf54f18857c"}
static Status **Create** (const FileSystemStoragePathSourceConfig
&config, std::unique\_ptr$<$
[FileSystemStoragePathSource](#classtensorflow_1_1serving_1_1FileSystemStoragePathSource)
$>$ $\ast$result)

[\[classtensorflow\_1\_1serving\_1\_1FileSystemStoragePathSource\_a0ddc7d29ad0b369a0f70b22e30083d3a\]]{#classtensorflow_1_1serving_1_1FileSystemStoragePathSource_a0ddc7d29ad0b369a0f70b22e30083d3a
label="classtensorflow_1_1serving_1_1FileSystemStoragePathSource_a0ddc7d29ad0b369a0f70b22e30083d3a"}
class **internal::FileSystemStoragePathSourceTestAccess**

A storage path source that aspires versions for a given set of
servables. For each servable, it monitors a given file-system base path.
It identifies base-path children whose name is a number (e.g. 123) and
emits the path corresponding to the largest number as the servables
single aspired version. (To do the file-system monitoring, it uses a
background thread that polls the file system periodically.)

For example, if a configured servables base path is /foo/bar, and a
file- system poll reveals child paths /foo/bar/baz, /foo/bar/123 and
/foo/bar/456, the aspired-versions callback is called with {456,
'̈/foo/bar/456'̈}. If, at any time, the base path is found to contain no
numerical children, the aspired-versions callback is called with an
empty versions list.

The configured set of servables to monitor can be updated at any time by
calling
[UpdateConfig()](#classtensorflow_1_1serving_1_1FileSystemStoragePathSource_ad29df4b1d9628b03723474db5a0d6ad0).
If any servables were present in the old config but not in the new one,
the source will immediately aspire zero versions for that servable
(causing it to be unloaded in the
[Manager](#classtensorflow_1_1serving_1_1Manager) that ultimately
consumes the aspired-versions calls).

[\[classtensorflow\_1\_1serving\_1\_1FileSystemStoragePathSource\_ad29df4b1d9628b03723474db5a0d6ad0\]]{#classtensorflow_1_1serving_1_1FileSystemStoragePathSource_ad29df4b1d9628b03723474db5a0d6ad0
label="classtensorflow_1_1serving_1_1FileSystemStoragePathSource_ad29df4b1d9628b03723474db5a0d6ad0"}

Status tensorflow::serving::FileSystemStoragePathSource::UpdateConfig (

config

)

Supplies a new config to use. The set of servables to monitor can be
changed at any time (see class comment for more information), but it is
illegal to change the file-system polling period once
SetAspiredVersionsCallback() has been called.

The documentation for this class was generated from the following files:

tensorflow\_serving/sources/storage\_path/file\_system\_storage\_path\_source.h

tensorflow\_serving/sources/storage\_path/file\_system\_storage\_path\_source.cc
