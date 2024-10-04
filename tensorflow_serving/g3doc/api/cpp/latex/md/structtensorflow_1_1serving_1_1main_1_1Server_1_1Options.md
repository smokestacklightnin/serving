::: {#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options}
:::

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options"}

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a858516addd0f9c709365fb1861070f02\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a858516addd0f9c709365fb1861070f02
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a858516addd0f9c709365fb1861070f02"}
tensorflow::int32 **grpc\_port** = 8500

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a4acac0be40d5c3de0a1d13b21bb7b1ae\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a4acac0be40d5c3de0a1d13b21bb7b1ae
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a4acac0be40d5c3de0a1d13b21bb7b1ae"}
tensorflow::string **grpc\_channel\_arguments**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_adbdd819bcdb419ed8b24863cc724d307\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_adbdd819bcdb419ed8b24863cc724d307
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_adbdd819bcdb419ed8b24863cc724d307"}
tensorflow::string **grpc\_socket\_path**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ac83d80fe2424a88e7f1e84beac11a2bf\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ac83d80fe2424a88e7f1e84beac11a2bf
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ac83d80fe2424a88e7f1e84beac11a2bf"}
tensorflow::int32 **grpc\_max\_threads** = 4. $\ast$
port::NumSchedulableCPUs()

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a40fb85d122da36e038fd724650538d19\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a40fb85d122da36e038fd724650538d19
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a40fb85d122da36e038fd724650538d19"}
tensorflow::int32 **http\_port** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a7aa16c82c39907ca8c78e9c9d9405ed4\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a7aa16c82c39907ca8c78e9c9d9405ed4
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a7aa16c82c39907ca8c78e9c9d9405ed4"}
tensorflow::int32 **http\_num\_threads** = 4. $\ast$
port::NumSchedulableCPUs()

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a66d001be5802e2662e447cf3b0f3f862\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a66d001be5802e2662e447cf3b0f3f862
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a66d001be5802e2662e447cf3b0f3f862"}
tensorflow::int32 **http\_timeout\_in\_ms** = 30000

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ab76613297053d282778c7b461434c949\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ab76613297053d282778c7b461434c949
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ab76613297053d282778c7b461434c949"}
bool **enable\_cors\_support** = false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ac69bf9a7572bf4818ae5584ee80b0768\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ac69bf9a7572bf4818ae5584ee80b0768
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ac69bf9a7572bf4818ae5584ee80b0768"}
bool **enable\_batching** = false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_abf6d0bb823d50d8ce3bd0cf4fd786990\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_abf6d0bb823d50d8ce3bd0cf4fd786990
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_abf6d0bb823d50d8ce3bd0cf4fd786990"}
bool **enable\_per\_model\_batching\_params** = false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_aa3d033165be73a01e1d030b16684ae89\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_aa3d033165be73a01e1d030b16684ae89
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_aa3d033165be73a01e1d030b16684ae89"}
bool **allow\_version\_labels\_for\_unavailable\_models** = false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a19d65c9f965b4160da7ed5d0964ae48d\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a19d65c9f965b4160da7ed5d0964ae48d
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a19d65c9f965b4160da7ed5d0964ae48d"}
bool **force\_allow\_any\_version\_labels\_for\_unavailable\_models** =
false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_aa6b4fea24a7ff7fa104957897271b518\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_aa6b4fea24a7ff7fa104957897271b518
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_aa6b4fea24a7ff7fa104957897271b518"}
float **per\_process\_gpu\_memory\_fraction** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ad72a6cccbf3cff2554a17e53687c9ea8\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ad72a6cccbf3cff2554a17e53687c9ea8
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ad72a6cccbf3cff2554a17e53687c9ea8"}
tensorflow::string **batching\_parameters\_file**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a0396a02d534f678da3c603f022ea3a98\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a0396a02d534f678da3c603f022ea3a98
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a0396a02d534f678da3c603f022ea3a98"}
tensorflow::string **model\_name**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ab253620c7ee20f386be6e2ff5de13bcc\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ab253620c7ee20f386be6e2ff5de13bcc
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ab253620c7ee20f386be6e2ff5de13bcc"}
tensorflow::int32 **num\_load\_threads** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a33fed24d69ae4517ba1f21db84ebfc2b\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a33fed24d69ae4517ba1f21db84ebfc2b
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a33fed24d69ae4517ba1f21db84ebfc2b"}
tensorflow::int32 **num\_unload\_threads** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_af7020b4dc82061bbd599bd6011ba6c2c\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af7020b4dc82061bbd599bd6011ba6c2c
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af7020b4dc82061bbd599bd6011ba6c2c"}
tensorflow::int32 **max\_num\_load\_retries** = 5

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a2854183a451d6da953d82e38a86a0475\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a2854183a451d6da953d82e38a86a0475
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a2854183a451d6da953d82e38a86a0475"}
int64\_t **load\_retry\_interval\_micros** = 1LL $\ast$ 60 $\ast$ 1000
$\ast$ 1000

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_af205e580d3b3c0748b44391d9c901869\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af205e580d3b3c0748b44391d9c901869
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af205e580d3b3c0748b44391d9c901869"}
tensorflow::int32 **file\_system\_poll\_wait\_seconds** = 1

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a6160a4d674a65cd1cef642d03c224d56\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a6160a4d674a65cd1cef642d03c224d56
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a6160a4d674a65cd1cef642d03c224d56"}
bool **flush\_filesystem\_caches** = true

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a134c72ab31e5f052672ec46561b3e7e3\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a134c72ab31e5f052672ec46561b3e7e3
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a134c72ab31e5f052672ec46561b3e7e3"}
tensorflow::string **model\_base\_path**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_af94726a871c57484632008c622e40f4c\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af94726a871c57484632008c622e40f4c
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af94726a871c57484632008c622e40f4c"}
tensorflow::string **saved\_model\_tags**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a3b85d5841a60a41fc42d79404280abf2\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a3b85d5841a60a41fc42d79404280abf2
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a3b85d5841a60a41fc42d79404280abf2"}
int64\_t **tensorflow\_session\_parallelism** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a44a733aa53ccc1d989efa79c1f5daa8d\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a44a733aa53ccc1d989efa79c1f5daa8d
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a44a733aa53ccc1d989efa79c1f5daa8d"}
int64\_t **tensorflow\_intra\_op\_parallelism** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a7ce89ba93a651242ea6155f0bbc0daf3\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a7ce89ba93a651242ea6155f0bbc0daf3
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a7ce89ba93a651242ea6155f0bbc0daf3"}
int64\_t **tensorflow\_inter\_op\_parallelism** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ada2d58e7e3e9d9bbdb085bab723793bb\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ada2d58e7e3e9d9bbdb085bab723793bb
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ada2d58e7e3e9d9bbdb085bab723793bb"}
tensorflow::string **platform\_config\_file**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a6c2a2f30fea36f6bbe940465943453a7\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a6c2a2f30fea36f6bbe940465943453a7
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a6c2a2f30fea36f6bbe940465943453a7"}
bool **use\_alts\_credentials** = false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_af94568162947af1c8200b4ee13ae3477\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af94568162947af1c8200b4ee13ae3477
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af94568162947af1c8200b4ee13ae3477"}
tensorflow::string **ssl\_config\_file**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a429a4552b3cc7c60c5016b1ac2555b41\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a429a4552b3cc7c60c5016b1ac2555b41
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a429a4552b3cc7c60c5016b1ac2555b41"}
string **model\_config\_file**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a0639412df7dfe82f2e8ef0679342a610\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a0639412df7dfe82f2e8ef0679342a610
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a0639412df7dfe82f2e8ef0679342a610"}
string **tensorflow\_session\_config\_file**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a2a77305f7f6d5fbce23eedfaa56f1fe1\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a2a77305f7f6d5fbce23eedfaa56f1fe1
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a2a77305f7f6d5fbce23eedfaa56f1fe1"}
tensorflow::int32 **fs\_model\_config\_poll\_wait\_seconds** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a96a05ae32da321d8f9885acc67f2f796\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a96a05ae32da321d8f9885acc67f2f796
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a96a05ae32da321d8f9885acc67f2f796"}
bool **enable\_model\_warmup** = true

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_af93aed1a1885fe97b36dbf8c72313a05\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af93aed1a1885fe97b36dbf8c72313a05
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_af93aed1a1885fe97b36dbf8c72313a05"}
tensorflow::int32 **num\_request\_iterations\_for\_warmup** = 0

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ade430ea430971bafe5cc45bd44b38058\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ade430ea430971bafe5cc45bd44b38058
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ade430ea430971bafe5cc45bd44b38058"}
tensorflow::string **monitoring\_config\_file**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a0ab877bec645ef2fa1d6733641450f6d\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a0ab877bec645ef2fa1d6733641450f6d
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a0ab877bec645ef2fa1d6733641450f6d"}
bool **enforce\_session\_run\_timeout** = true

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a665a204b699f3a91fdcda08a4cae0a05\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a665a204b699f3a91fdcda08a4cae0a05
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a665a204b699f3a91fdcda08a4cae0a05"}
bool **remove\_unused\_fields\_from\_bundle\_metagraph** = true

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a47eafe2907bc8e137d46f95651072229\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a47eafe2907bc8e137d46f95651072229
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a47eafe2907bc8e137d46f95651072229"}
bool **prefer\_tflite\_model** = false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a8b52fe3920a81d8e1de7f2790e0bd056\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a8b52fe3920a81d8e1de7f2790e0bd056
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a8b52fe3920a81d8e1de7f2790e0bd056"}
tensorflow::int32 **num\_tflite\_pools** = port::NumSchedulableCPUs()

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ad3c77d766df21b8c0e4f12cf3896e289\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ad3c77d766df21b8c0e4f12cf3896e289
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ad3c77d766df21b8c0e4f12cf3896e289"}
tensorflow::int32 **num\_tflite\_interpreters\_per\_pool** = 1

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_abced08a72b9096cb0839e2ea8f34fd6b\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_abced08a72b9096cb0839e2ea8f34fd6b
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_abced08a72b9096cb0839e2ea8f34fd6b"}
tensorflow::string **thread\_pool\_factory\_config\_file**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_afef47674cd381b95490671d6bec9f6aa\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_afef47674cd381b95490671d6bec9f6aa
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_afef47674cd381b95490671d6bec9f6aa"}
bool **enable\_signature\_method\_name\_check** = false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a61a39305118199a067581c6f3f9f9f0b\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a61a39305118199a067581c6f3f9f9f0b
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a61a39305118199a067581c6f3f9f9f0b"}
bool **enable\_profiler** = true

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_adf07f562821d9635579709cc78403cef\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_adf07f562821d9635579709cc78403cef
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_adf07f562821d9635579709cc78403cef"}
tensorflow::string **mixed\_precision**

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_ae06d7be2f272a9f0db9533f6f9538995\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ae06d7be2f272a9f0db9533f6f9538995
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_ae06d7be2f272a9f0db9533f6f9538995"}
bool **skip\_initialize\_tpu** = false

[\[structtensorflow\_1\_1serving\_1\_1main\_1\_1Server\_1\_1Options\_a1d796f34d5231ffb49c7a9c27053df02\]]{#structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a1d796f34d5231ffb49c7a9c27053df02
label="structtensorflow_1_1serving_1_1main_1_1Server_1_1Options_a1d796f34d5231ffb49c7a9c27053df02"}
bool **enable\_grpc\_healthcheck\_service** = false

The documentation for this struct was generated from the following
files:

tensorflow\_serving/model\_servers/server.h

tensorflow\_serving/model\_servers/server.cc
