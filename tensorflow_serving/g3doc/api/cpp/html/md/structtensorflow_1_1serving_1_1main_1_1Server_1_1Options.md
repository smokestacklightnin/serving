::: {#top}
::: {#titlearea}
+-----------------------------------------------------------------------+
| ::: {#projectname}                                                    |
| My Project                                                            |
| :::                                                                   |
+-----------------------------------------------------------------------+
:::

::: {#main-nav}
:::

::: {#MSearchSelectWindow onmouseover="return searchBox.OnSearchSelectShow()" onmouseout="return searchBox.OnSearchSelectHide()" onkeydown="return searchBox.OnSearchSelectKey(event)"}
:::

::: {#MSearchResultsWindow}
:::

::: {#nav-path .navpath}
-   **tensorflow**
-   **serving**
-   **main**
-   [Server](classtensorflow_1_1serving_1_1main_1_1Server.html){.el}
-   [Options](structtensorflow_1_1serving_1_1main_1_1Server_1_1Options.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Attributes](#pub-attribs) \| [List of all
members](structtensorflow_1_1serving_1_1main_1_1Server_1_1Options-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::main::Server::Options Struct Reference
:::
:::
:::

::: {.contents}
[]{#pub-attribs} Public Attributes {#public-attributes .groupheader}
----------------------------------
:::

[]{#a858516addd0f9c709365fb1861070f02} tensorflow::int32 

**grpc\_port** = 8500

 

[]{#a4acac0be40d5c3de0a1d13b21bb7b1ae} tensorflow::string 

**grpc\_channel\_arguments**

 

[]{#adbdd819bcdb419ed8b24863cc724d307} tensorflow::string 

**grpc\_socket\_path**

 

[]{#ac83d80fe2424a88e7f1e84beac11a2bf} tensorflow::int32 

**grpc\_max\_threads** = 4.0 \* port::NumSchedulableCPUs()

 

[]{#a40fb85d122da36e038fd724650538d19} tensorflow::int32 

**http\_port** = 0

 

[]{#a7aa16c82c39907ca8c78e9c9d9405ed4} tensorflow::int32 

**http\_num\_threads** = 4.0 \* port::NumSchedulableCPUs()

 

[]{#a66d001be5802e2662e447cf3b0f3f862} tensorflow::int32 

**http\_timeout\_in\_ms** = 30000

 

[]{#ab76613297053d282778c7b461434c949} bool 

**enable\_cors\_support** = false

 

[]{#ac69bf9a7572bf4818ae5584ee80b0768} bool 

**enable\_batching** = false

 

[]{#abf6d0bb823d50d8ce3bd0cf4fd786990} bool 

**enable\_per\_model\_batching\_params** = false

 

[]{#aa3d033165be73a01e1d030b16684ae89} bool 

**allow\_version\_labels\_for\_unavailable\_models** = false

 

[]{#a19d65c9f965b4160da7ed5d0964ae48d} bool 

**force\_allow\_any\_version\_labels\_for\_unavailable\_models** = false

 

[]{#aa6b4fea24a7ff7fa104957897271b518} float 

**per\_process\_gpu\_memory\_fraction** = 0

 

[]{#ad72a6cccbf3cff2554a17e53687c9ea8} tensorflow::string 

**batching\_parameters\_file**

 

[]{#a0396a02d534f678da3c603f022ea3a98} tensorflow::string 

**model\_name**

 

[]{#ab253620c7ee20f386be6e2ff5de13bcc} tensorflow::int32 

**num\_load\_threads** = 0

 

[]{#a33fed24d69ae4517ba1f21db84ebfc2b} tensorflow::int32 

**num\_unload\_threads** = 0

 

[]{#af7020b4dc82061bbd599bd6011ba6c2c} tensorflow::int32 

**max\_num\_load\_retries** = 5

 

[]{#a2854183a451d6da953d82e38a86a0475} int64\_t 

**load\_retry\_interval\_micros** = 1LL \* 60 \* 1000 \* 1000

 

[]{#af205e580d3b3c0748b44391d9c901869} tensorflow::int32 

**file\_system\_poll\_wait\_seconds** = 1

 

[]{#a6160a4d674a65cd1cef642d03c224d56} bool 

**flush\_filesystem\_caches** = true

 

[]{#a134c72ab31e5f052672ec46561b3e7e3} tensorflow::string 

**model\_base\_path**

 

[]{#af94726a871c57484632008c622e40f4c} tensorflow::string 

**saved\_model\_tags**

 

[]{#a3b85d5841a60a41fc42d79404280abf2} int64\_t 

**tensorflow\_session\_parallelism** = 0

 

[]{#a44a733aa53ccc1d989efa79c1f5daa8d} int64\_t 

**tensorflow\_intra\_op\_parallelism** = 0

 

[]{#a7ce89ba93a651242ea6155f0bbc0daf3} int64\_t 

**tensorflow\_inter\_op\_parallelism** = 0

 

[]{#ada2d58e7e3e9d9bbdb085bab723793bb} tensorflow::string 

**platform\_config\_file**

 

[]{#a6c2a2f30fea36f6bbe940465943453a7} bool 

**use\_alts\_credentials** = false

 

[]{#af94568162947af1c8200b4ee13ae3477} tensorflow::string 

**ssl\_config\_file**

 

[]{#a429a4552b3cc7c60c5016b1ac2555b41} string 

**model\_config\_file**

 

[]{#a0639412df7dfe82f2e8ef0679342a610} string 

**tensorflow\_session\_config\_file**

 

[]{#a2a77305f7f6d5fbce23eedfaa56f1fe1} tensorflow::int32 

**fs\_model\_config\_poll\_wait\_seconds** = 0

 

[]{#a96a05ae32da321d8f9885acc67f2f796} bool 

**enable\_model\_warmup** = true

 

[]{#af93aed1a1885fe97b36dbf8c72313a05} tensorflow::int32 

**num\_request\_iterations\_for\_warmup** = 0

 

[]{#ade430ea430971bafe5cc45bd44b38058} tensorflow::string 

**monitoring\_config\_file**

 

[]{#a0ab877bec645ef2fa1d6733641450f6d} bool 

**enforce\_session\_run\_timeout** = true

 

[]{#a665a204b699f3a91fdcda08a4cae0a05} bool 

**remove\_unused\_fields\_from\_bundle\_metagraph** = true

 

[]{#a47eafe2907bc8e137d46f95651072229} bool 

**prefer\_tflite\_model** = false

 

[]{#a8b52fe3920a81d8e1de7f2790e0bd056} tensorflow::int32 

**num\_tflite\_pools** = port::NumSchedulableCPUs()

 

[]{#ad3c77d766df21b8c0e4f12cf3896e289} tensorflow::int32 

**num\_tflite\_interpreters\_per\_pool** = 1

 

[]{#abced08a72b9096cb0839e2ea8f34fd6b} tensorflow::string 

**thread\_pool\_factory\_config\_file**

 

[]{#afef47674cd381b95490671d6bec9f6aa} bool 

**enable\_signature\_method\_name\_check** = false

 

[]{#a61a39305118199a067581c6f3f9f9f0b} bool 

**enable\_profiler** = true

 

[]{#adf07f562821d9635579709cc78403cef} tensorflow::string 

**mixed\_precision**

 

[]{#ae06d7be2f272a9f0db9533f6f9538995} bool 

**skip\_initialize\_tpu** = false

 

[]{#a1d796f34d5231ffb49c7a9c27053df02} bool 

**enable\_grpc\_healthcheck\_service** = false

 

------------------------------------------------------------------------

The documentation for this struct was generated from the following
files:

-   tensorflow\_serving/model\_servers/[server.h](server_8h_source.html){.el}
-   tensorflow\_serving/model\_servers/server.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
