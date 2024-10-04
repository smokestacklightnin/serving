::: {#classtensorflow_1_1serving_1_1net__http_1_1ZLib}
:::

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib"}

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a31c05ad244aec8bf042b103dc898ea0b\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a31c05ad244aec8bf042b103dc898ea0b
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a31c05ad244aec8bf042b103dc898ea0b"}
void **Reinit** ()

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a6a3d692688249d5e9a4e2d8fb8738289\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a6a3d692688249d5e9a4e2d8fb8738289
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a6a3d692688249d5e9a4e2d8fb8738289"}
void **Reset** ()

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_ae890d4043056825c0e323268e9c4d3a3\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_ae890d4043056825c0e323268e9c4d3a3
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_ae890d4043056825c0e323268e9c4d3a3"}
void **SetDontHideStreamEnd** ()

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a2d7b9150253350ae8cc467444d65c0b8\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a2d7b9150253350ae8cc467444d65c0b8
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a2d7b9150253350ae8cc467444d65c0b8"}
void **SetCompressionLevel** (int level)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a8eaed93efb16321185f47ad1a4589fa7\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a8eaed93efb16321185f47ad1a4589fa7
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a8eaed93efb16321185f47ad1a4589fa7"}
void **SetCompressionWindowSizeInBits** (int bits)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_ac64ce9240ee4355ec8a34871fe83d1bb\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_ac64ce9240ee4355ec8a34871fe83d1bb
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_ac64ce9240ee4355ec8a34871fe83d1bb"}
void **SetCompressionMemLevel** (int level)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a2fb04f8bf8b5035409c8d645a147fbd6\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a2fb04f8bf8b5035409c8d645a147fbd6
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a2fb04f8bf8b5035409c8d645a147fbd6"}
int **MinFooterSize** () const

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a2705eb0e1fadf143cde793483d73de5e\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a2705eb0e1fadf143cde793483d73de5e
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a2705eb0e1fadf143cde793483d73de5e"}
int **Compress** (Bytef $\ast$dest, uLongf $\ast$destLen, const Bytef
$\ast$source, uLong sourceLen)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_af63e80625cc05e276ab680f5b4e159c3\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_af63e80625cc05e276ab680f5b4e159c3
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_af63e80625cc05e276ab680f5b4e159c3"}
int **Uncompress** (Bytef $\ast$dest, uLongf $\ast$destLen, const Bytef
$\ast$source, uLong sourceLen)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a1d60760865777a5122e09af5e7154449\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a1d60760865777a5122e09af5e7154449
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a1d60760865777a5122e09af5e7154449"}
uLongf **GzipUncompressedLength** (const Bytef $\ast$source, uLong len)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a42af43fa2696040fcc4a63984bad031b\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a42af43fa2696040fcc4a63984bad031b
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a42af43fa2696040fcc4a63984bad031b"}
int **UncompressGzipAndAllocate** (Bytef $\ast$$\ast$dest, uLongf
$\ast$destLen, const Bytef $\ast$source, uLong sourceLen)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a0ddfe46cb4f8cb8b18831284a6011b60\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a0ddfe46cb4f8cb8b18831284a6011b60
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a0ddfe46cb4f8cb8b18831284a6011b60"}
int **CompressAtMost** (Bytef $\ast$dest, uLongf $\ast$destLen, const
Bytef $\ast$source, uLong $\ast$sourceLen)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a880542fb11b47e62ab372a84dd78acf8\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a880542fb11b47e62ab372a84dd78acf8
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a880542fb11b47e62ab372a84dd78acf8"}
int **CompressChunkDone** (Bytef $\ast$dest, uLongf $\ast$destLen)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a5d435e9335e3caeb4b75df8d6b4b13b8\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a5d435e9335e3caeb4b75df8d6b4b13b8
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a5d435e9335e3caeb4b75df8d6b4b13b8"}
int **UncompressAtMost** (Bytef $\ast$dest, uLongf $\ast$destLen, const
Bytef $\ast$source, uLong $\ast$sourceLen)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a6cdf2a91cba4d35f69a1e59a0757c8e3\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a6cdf2a91cba4d35f69a1e59a0757c8e3
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a6cdf2a91cba4d35f69a1e59a0757c8e3"}
bool **UncompressChunkDone** ()

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a510d121a5fbed5c09c29770a7fcb1c75\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a510d121a5fbed5c09c29770a7fcb1c75
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a510d121a5fbed5c09c29770a7fcb1c75"}
bool **first\_chunk** () const

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a42abca7649d9427970f5f8dbfb05ce68\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a42abca7649d9427970f5f8dbfb05ce68
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a42abca7649d9427970f5f8dbfb05ce68"}
bool **IsGzipFooterComplete** () const

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_aa69977b16d68e44e191b0cd1ce159ac4\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_aa69977b16d68e44e191b0cd1ce159ac4
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_aa69977b16d68e44e191b0cd1ce159ac4"}
bool **IsGzipFooterValid** () const

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a4ecdbdb9f88913c95f7c426cf43578e8\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a4ecdbdb9f88913c95f7c426cf43578e8
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a4ecdbdb9f88913c95f7c426cf43578e8"}
uLong **uncompressed\_size** () const

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a3618e1d59f1228bdc86a23d59ab45d85\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a3618e1d59f1228bdc86a23d59ab45d85
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a3618e1d59f1228bdc86a23d59ab45d85"}
static uLong **MinCompressbufSize** (uLong uncompress\_size)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a1dd79d9afef1ccd3002fbdb080d28c18\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a1dd79d9afef1ccd3002fbdb080d28c18
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a1dd79d9afef1ccd3002fbdb080d28c18"}
static bool **HasGzipHeader** (const char $\ast$source, int sourceLen)

[\[classtensorflow\_1\_1serving\_1\_1net\_\_http\_1\_1ZLib\_a4aa2412c480c52a4f59c06907ab871e6\]]{#classtensorflow_1_1serving_1_1net__http_1_1ZLib_a4aa2412c480c52a4f59c06907ab871e6
label="classtensorflow_1_1serving_1_1net__http_1_1ZLib_a4aa2412c480c52a4f59c06907ab871e6"}
static constexpr int64\_t **kMaxUncompressedBytes** = 100 $\ast$ 1024
$\ast$ 1024

The documentation for this class was generated from the following files:

tensorflow\_serving/util/net\_http/compression/gzip\_zlib.h

tensorflow\_serving/util/net\_http/compression/gzip\_zlib.cc
