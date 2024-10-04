::: {#classtensorflow_1_1serving_1_1SavedModelBundleFactory}
:::

[\[classtensorflow\_1\_1serving\_1\_1SavedModelBundleFactory\]]{#classtensorflow_1_1serving_1_1SavedModelBundleFactory
label="classtensorflow_1_1serving_1_1SavedModelBundleFactory"}

\#include $<$saved\_model\_bundle\_factory.h$>$

Status
[CreateSavedModelBundle](#classtensorflow_1_1serving_1_1SavedModelBundleFactory_aa27eec255c83cd1d2f249a2e4a2d0526)
(const string &path, std::unique\_ptr$<$ SavedModelBundle $>$
$\ast$bundle)

Status
[CreateSavedModelBundleWithMetadata](#classtensorflow_1_1serving_1_1SavedModelBundleFactory_a88da623c02425fe3d01a21e13b956d49)
(const
[Loader::Metadata](#structtensorflow_1_1serving_1_1Loader_1_1Metadata)
&metadata, const string &path, std::unique\_ptr$<$ SavedModelBundle $>$
$\ast$bundle)

Status
[EstimateResourceRequirement](#classtensorflow_1_1serving_1_1SavedModelBundleFactory_a4b897842868d8f090ebe972974e03bf7)
(const string &path, ResourceAllocation $\ast$estimate) const

[\[classtensorflow\_1\_1serving\_1\_1SavedModelBundleFactory\_a36f97e1012459789c56ba07eef4b834c\]]{#classtensorflow_1_1serving_1_1SavedModelBundleFactory_a36f97e1012459789c56ba07eef4b834c
label="classtensorflow_1_1serving_1_1SavedModelBundleFactory_a36f97e1012459789c56ba07eef4b834c"}
const SessionBundleConfig & **config** () const

[\[classtensorflow\_1\_1serving\_1\_1SavedModelBundleFactory\_a1b7a4e8f7f3bf2ce30570d8b1391de78\]]{#classtensorflow_1_1serving_1_1SavedModelBundleFactory_a1b7a4e8f7f3bf2ce30570d8b1391de78
label="classtensorflow_1_1serving_1_1SavedModelBundleFactory_a1b7a4e8f7f3bf2ce30570d8b1391de78"}
SessionBundleConfig & **mutable\_config** ()

static Status
[Create](#classtensorflow_1_1serving_1_1SavedModelBundleFactory_a234678b40af9995c21a72d265540fdb9)
(const SessionBundleConfig &config, std::unique\_ptr$<$
[SavedModelBundleFactory](#classtensorflow_1_1serving_1_1SavedModelBundleFactory)
$>$ $\ast$factory)

A factory that creates SavedModelBundles from SavedModel or
[SessionBundle](#structtensorflow_1_1serving_1_1SessionBundle) export
paths.

The emitted sessions only support Run(), and although not enforced it is
expected that the client will only make non-mutating Run() calls. (If
this restriction, which weve added as a safety measure, is problematic
for your use-case please contact the TensorFlow Serving team to discuss
disabling it.)

If the config calls for batching, the emitted sessions automatically
batch Run() calls behind the scenes, using a SharedBatchScheduler owned
by the factory. The config.num\_batch\_threads threads are shared across
all session instances created by this factory. However, each session has
its own dedicated queue of size config.max\_enqueued\_batches.

The factory can also estimate the resource (e.g. RAM) requirements of a
SavedModelBundle based on the SavedModel (i.e. prior to loading the
session).

This class is thread-safe.

[\[classtensorflow\_1\_1serving\_1\_1SavedModelBundleFactory\_a234678b40af9995c21a72d265540fdb9\]]{#classtensorflow_1_1serving_1_1SavedModelBundleFactory_a234678b40af9995c21a72d265540fdb9
label="classtensorflow_1_1serving_1_1SavedModelBundleFactory_a234678b40af9995c21a72d265540fdb9"}

Status tensorflow::serving::SavedModelBundleFactory::Create (

config,

factory

)

Instantiates a
[SavedModelBundleFactory](#classtensorflow_1_1serving_1_1SavedModelBundleFactory)
using a config.

Parameters *config* & Config with initialization options.\
*factory* & Newly created factory if the returned Status is OK.\

[\[classtensorflow\_1\_1serving\_1\_1SavedModelBundleFactory\_aa27eec255c83cd1d2f249a2e4a2d0526\]]{#classtensorflow_1_1serving_1_1SavedModelBundleFactory_aa27eec255c83cd1d2f249a2e4a2d0526
label="classtensorflow_1_1serving_1_1SavedModelBundleFactory_aa27eec255c83cd1d2f249a2e4a2d0526"}

Status
tensorflow::serving::SavedModelBundleFactory::CreateSavedModelBundle (

path,

bundle

)

Instantiates a bundle from a given export or SavedModel path.

Parameters *path* & Path to the model.\
*bundle* & Newly created SavedModelBundle if the returned Status is OK.\

[\[classtensorflow\_1\_1serving\_1\_1SavedModelBundleFactory\_a88da623c02425fe3d01a21e13b956d49\]]{#classtensorflow_1_1serving_1_1SavedModelBundleFactory_a88da623c02425fe3d01a21e13b956d49
label="classtensorflow_1_1serving_1_1SavedModelBundleFactory_a88da623c02425fe3d01a21e13b956d49"}

Status
tensorflow::serving::SavedModelBundleFactory::CreateSavedModelBundleWithMetadata
(

metadata,

path,

bundle

)

Instantiates a bundle from a given export or SavedModel path and the
given metadata.

Parameters *metadata* & Metadata to be associated with the bundle.\
*path* & Path to the model.\
*bundle* & Newly created SavedModelBundle if the returned Status is OK.\

[\[classtensorflow\_1\_1serving\_1\_1SavedModelBundleFactory\_a4b897842868d8f090ebe972974e03bf7\]]{#classtensorflow_1_1serving_1_1SavedModelBundleFactory_a4b897842868d8f090ebe972974e03bf7
label="classtensorflow_1_1serving_1_1SavedModelBundleFactory_a4b897842868d8f090ebe972974e03bf7"}

Status
tensorflow::serving::SavedModelBundleFactory::EstimateResourceRequirement
(

path,

estimate

) const

Estimates the resources a SavedModel bundle will use once loaded, from
its export path.

Parameters *path* & Path to the model.\
*estimate* & Output resource usage estimates. Different kinds of
resources (e.g. CPU, RAM, etc.) may get populated.\

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/saved\_model\_bundle\_factory.h

tensorflow\_serving/servables/tensorflow/saved\_model\_bundle\_factory.cc
