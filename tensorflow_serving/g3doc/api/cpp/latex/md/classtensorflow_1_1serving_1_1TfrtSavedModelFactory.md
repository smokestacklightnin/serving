::: {#classtensorflow_1_1serving_1_1TfrtSavedModelFactory}
:::

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory"}

\#include $<$tfrt\_saved\_model\_factory.h$>$

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_ab74f14db2692406da470b58598de8480\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_ab74f14db2692406da470b58598de8480
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_ab74f14db2692406da470b58598de8480"}
using **Batcher** = SharedBatchScheduler$<$
[SavedModelBatchingTask](#structtensorflow_1_1serving_1_1SavedModelBatchingTask)
$>$

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_a0e0170fbaf2589f5a0847023e4d91c1c\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_a0e0170fbaf2589f5a0847023e4d91c1c
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_a0e0170fbaf2589f5a0847023e4d91c1c"}
**TfrtSavedModelFactory** (const TfrtSavedModelConfig &config,
std::shared\_ptr$<$ Batcher $>$ batch\_scheduler, std::unique\_ptr$<$
[ThreadPoolFactory](#classtensorflow_1_1serving_1_1ThreadPoolFactory)
$>$ thread\_pool\_factory)

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_aa148cff5fb3ab4122762ac9cf360b75b\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_aa148cff5fb3ab4122762ac9cf360b75b
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_aa148cff5fb3ab4122762ac9cf360b75b"}
**TfrtSavedModelFactory** (const TfrtSavedModelConfig &config,
std::shared\_ptr$<$ Batcher $>$ batch\_scheduler, std::unique\_ptr$<$
[ThreadPoolFactory](#classtensorflow_1_1serving_1_1ThreadPoolFactory)
$>$ thread\_pool\_factory, std::function$<$ std::unique\_ptr$<$
[RequestRecorder](#classtensorflow_1_1serving_1_1RequestRecorder)
$>$([TfrtSavedModelServable](#classtensorflow_1_1serving_1_1TfrtSavedModelServable)
&)$>$ recorder\_creator)

virtual absl::Status
[CreateTfrtSavedModelWithMetadata](#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_affd90c58362c83fb9949bc9892201386)
(const
[Loader::Metadata](#structtensorflow_1_1serving_1_1Loader_1_1Metadata)
&metadata, const string &path, std::unique\_ptr$<$
[Servable](#classtensorflow_1_1serving_1_1Servable) $>$ $\ast$servable)

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_a580da5425b4fac83100cdb6f3065e6a2\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_a580da5425b4fac83100cdb6f3065e6a2
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_a580da5425b4fac83100cdb6f3065e6a2"}
absl::Status **CreateTfrtSavedModelWithMetadata** (const
[Loader::Metadata](#structtensorflow_1_1serving_1_1Loader_1_1Metadata)
&metadata, const string &path, std::unique\_ptr$<$
tfrt\_stub::SavedModel $>$ $\ast$saved\_model)

absl::Status
[EstimateResourceRequirement](#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_aa1451f446252c259f225722b9cd07aaf)
(const string &path, ResourceAllocation $\ast$estimate) const

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_a997159ccadc111184b10717926e502f4\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_a997159ccadc111184b10717926e502f4
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_a997159ccadc111184b10717926e502f4"}
const TfrtSavedModelConfig & **config** () const

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_a29020fcd753a5d2d630f753d447c6ebc\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_a29020fcd753a5d2d630f753d447c6ebc
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_a29020fcd753a5d2d630f753d447c6ebc"}
TfrtSavedModelConfig & **mutable\_config** ()

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_acdff7e86f61c57cd4bae187295a40d39\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_acdff7e86f61c57cd4bae187295a40d39
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_acdff7e86f61c57cd4bae187295a40d39"}
absl::string\_view **GetServingResourceType** () const

static absl::Status
[Create](#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_ad168a4902febebaa51745428a5da5f17)
(const TfrtSavedModelConfig &config, std::unique\_ptr$<$
[TfrtSavedModelFactory](#classtensorflow_1_1serving_1_1TfrtSavedModelFactory)
$>$ $\ast$factory)

A factory that creates tfrt\_stub::SavedModel from SavedModel export
paths.

The factory can also estimate the resource (e.g. RAM) requirements of a
tfrt\_stub::SavedModel based on the SavedModel (i.e. prior to loading
the session).

This class is thread-safe.

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_ad168a4902febebaa51745428a5da5f17\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_ad168a4902febebaa51745428a5da5f17
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_ad168a4902febebaa51745428a5da5f17"}

absl::Status tensorflow::serving::TfrtSavedModelFactory::Create (

config,

factory

)

Instantiates a
[TfrtSavedModelFactory](#classtensorflow_1_1serving_1_1TfrtSavedModelFactory)
using a config.

Parameters *config* & Config with initialization options.\
*factory* & Newly created factory if the returned Status is OK.\

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_affd90c58362c83fb9949bc9892201386\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_affd90c58362c83fb9949bc9892201386
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_affd90c58362c83fb9949bc9892201386"}

virtual absl::Status
tensorflow::serving::TfrtSavedModelFactory::CreateTfrtSavedModelWithMetadata
(

metadata,

path,

servable

)

Instantiates a tfrt\_stub::SavedModel from a given export or SavedModel
path and the given metadata.

Parameters *metadata* & Metadata to be associated with the
saved\_model.\
*path* & Path to the model.\
*servable* & Newly created
[Servable](#classtensorflow_1_1serving_1_1Servable) if the returned
Status is OK.\

[\[classtensorflow\_1\_1serving\_1\_1TfrtSavedModelFactory\_aa1451f446252c259f225722b9cd07aaf\]]{#classtensorflow_1_1serving_1_1TfrtSavedModelFactory_aa1451f446252c259f225722b9cd07aaf
label="classtensorflow_1_1serving_1_1TfrtSavedModelFactory_aa1451f446252c259f225722b9cd07aaf"}

absl::Status
tensorflow::serving::TfrtSavedModelFactory::EstimateResourceRequirement
(

path,

estimate

) const

Estimates the resources a SavedModel will use once loaded, from its
export path.

Parameters *path* & Path to the model.\
*estimate* & Output resource usage estimates. Different kinds of
resources (e.g. CPU, RAM, etc.) may get populated.\

The documentation for this class was generated from the following files:

tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_factory.h

tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_factory.cc
