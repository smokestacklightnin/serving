::: {#classtensorflow_1_1serving_1_1ThreadSafeStatus}
:::

[\[classtensorflow\_1\_1serving\_1\_1ThreadSafeStatus\]]{#classtensorflow_1_1serving_1_1ThreadSafeStatus
label="classtensorflow_1_1serving_1_1ThreadSafeStatus"}

[\[classtensorflow\_1\_1serving\_1\_1ThreadSafeStatus\_a54e3cff923412449915d4cb329c9ed02\]]{#classtensorflow_1_1serving_1_1ThreadSafeStatus_a54e3cff923412449915d4cb329c9ed02
label="classtensorflow_1_1serving_1_1ThreadSafeStatus_a54e3cff923412449915d4cb329c9ed02"}
const Status & **status** () const &TF\_LOCKS\_EXCLUDED(mutex\_)

[\[classtensorflow\_1\_1serving\_1\_1ThreadSafeStatus\_aadd5d57f100bf4977eb9ed464de0bb68\]]{#classtensorflow_1_1serving_1_1ThreadSafeStatus_aadd5d57f100bf4977eb9ed464de0bb68
label="classtensorflow_1_1serving_1_1ThreadSafeStatus_aadd5d57f100bf4977eb9ed464de0bb68"}
Status **status** () &&TF\_LOCKS\_EXCLUDED(mutex\_)

[\[classtensorflow\_1\_1serving\_1\_1ThreadSafeStatus\_ad16ab895d8ba2f2fe8b74948d8fd602f\]]{#classtensorflow_1_1serving_1_1ThreadSafeStatus_ad16ab895d8ba2f2fe8b74948d8fd602f
label="classtensorflow_1_1serving_1_1ThreadSafeStatus_ad16ab895d8ba2f2fe8b74948d8fd602f"}
void **Update** (const Status &new\_status) TF\_LOCKS\_EXCLUDED(mutex\_)

[\[classtensorflow\_1\_1serving\_1\_1ThreadSafeStatus\_aff32ed57fbb4d3ae5107c2abd78e83ba\]]{#classtensorflow_1_1serving_1_1ThreadSafeStatus_aff32ed57fbb4d3ae5107c2abd78e83ba
label="classtensorflow_1_1serving_1_1ThreadSafeStatus_aff32ed57fbb4d3ae5107c2abd78e83ba"}
void **Update** (Status &&new\_status) TF\_LOCKS\_EXCLUDED(mutex\_)

The documentation for this class was generated from the following files:

tensorflow\_serving/batching/threadsafe\_status.h

tensorflow\_serving/batching/threadsafe\_status.cc
