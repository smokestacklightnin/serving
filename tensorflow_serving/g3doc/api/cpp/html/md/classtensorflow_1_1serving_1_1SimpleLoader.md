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
-   [SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Types](#pub-types) \| [Public Member Functions](#pub-methods) \|
[Static Public Member Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1SimpleLoader-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::SimpleLoader\< ServableType \> Class Template
Reference
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::SimpleLoader\< ServableType
\>:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1SimpleLoader__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::SimpleLoader\<
ServableType \>:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1SimpleLoader__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------
:::

[]{#a41233d05569814753928a67a414281a9} using 

**Creator** = std::function\< Status(std::unique\_ptr\< ServableType \>
\*)\>

 

[]{#a4623eb7f1ee9169db1d9f23e0f377922} using 

**CreatorWithMetadata** = std::function\< Status(const
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el}
&, std::unique\_ptr\< ServableType \> \*)\>

 

[]{#ab25158ab5062f7e125d5771ebef4c571} using 

**CreatorVariant** = absl::variant\< Creator, CreatorWithMetadata \>

 

[]{#ad56b75f604ff95b4740573209efd3fd5} using 

**ResourceEstimator** = std::function\< Status(ResourceAllocation \*)\>

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

[]{#ab128232d2103f28712aca27d74a4d255}  

**SimpleLoader** (Creator creator, ResourceEstimator
resource\_estimator)

 

[]{#a9125d0e74cf2f7cd41ddaae3902713cb}  

**SimpleLoader** (CreatorWithMetadata creator\_with\_metadata,
ResourceEstimator resource\_estimator)

 

[]{#a14d1a5400554740aceae0d60840e1832}  

**SimpleLoader** (Creator creator, ResourceEstimator
resource\_estimator, ResourceEstimator post\_load\_resource\_estimator)

 

[]{#afd1e11ebf64eed6be7e63d32df4c8a77}  

**SimpleLoader** (CreatorWithMetadata creator\_with\_metadata,
ResourceEstimator resource\_estimator, ResourceEstimator
post\_load\_resource\_estimator)

 

[]{#a761d945b99d3cab3e8ec1b4e385f5ca2}  

**SimpleLoader** (CreatorVariant creator\_variant, ResourceEstimator
resource\_estimator, absl::optional\< ResourceEstimator \>
post\_load\_resource\_estimator)

 

Status 

[EstimateResources](classtensorflow_1_1serving_1_1SimpleLoader.html#a05ede6c604d05037f59fe13472b48935){.el}
(ResourceAllocation \*estimate) const override

 

Status 

[Load](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el}
() override

 

Status 

[LoadWithMetadata](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24){.el}
(const
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el}
&metadata) override

 

void 

[Unload](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.el}
() override

 

[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el} 

[servable](classtensorflow_1_1serving_1_1SimpleLoader.html#a914a9107be7cfeb587998934be9d9fee){.el}
() override

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}

virtual 

[\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.el}
()=default

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a9df494e930b1c23df38685a10d7c9614} static ResourceEstimator 

**EstimateNoResources** ()

 

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a05ede6c604d05037f59fe13472b48935}

[[◆ ](#a05ede6c604d05037f59fe13472b48935)]{.permalink}EstimateResources() {#estimateresources .memtitle}
-------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename ServableType \>
:::

+-----------------------------------+-----------------------------------+
|   ------------------------        | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------ --- ---------------- |                                   |
| -------- ------------ --- ------- |                                   |
|   Status [tensorflow::se          |                                   |
| rving::SimpleLoader](classtensorf |                                   |
| low_1_1serving_1_1SimpleLoader.ht |                                   |
| ml){.el}\< ServableType \>::Estim |                                   |
| ateResources   (   ResourceAlloca |                                   |
| tion \*    *estimate*   )   const |                                   |
|   ------------------------        |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------ --- ---------------- |                                   |
| -------- ------------ --- ------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Estimates the resources a servable will use.

IMPORTANT: This method\'s implementation must obey following
requirements, which enable the serving system to reason correctly about
which servables can be loaded safely:

1.  The estimate must represent an upper bound on the actual value.
2.  Prior to load, the estimate may include resources that are not bound
    to any specific device instance, e.g. RAM on one of the two GPUs.
3.  While loaded, for any devices with multiple instances (e.g. two
    GPUs), the estimate must specify the instance to which each resource
    is bound.
4.  The estimate must be monotonically non-increasing, i.e. it cannot
    increase over time. Reasons to have it potentially decrease over
    time

    Returns
    :   an estimate of the resources the servable will consume once
        loaded. If the servable has already been loaded, returns an
        estimate of the actual resource usage.

Implements
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40){.el}.
:::
:::

[]{#ada69d680b17f2e054faef889f135cb74}

[[◆ ](#ada69d680b17f2e054faef889f135cb74)]{.permalink}Load() {#load .memtitle}
------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename ServableType \>
:::

+-----------------------------------+-----------------------------------+
|   -----------------------         | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
|   Status [tensorflow::s           |                                   |
| erving::SimpleLoader](classtensor |                                   |
| flow_1_1serving_1_1SimpleLoader.h |                                   |
| tml){.el}\< ServableType \>::Load |                                   |
|   -----------------------         |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Fetches any data that needs to be loaded before using the servable
returned by
[servable()](classtensorflow_1_1serving_1_1SimpleLoader.html#a914a9107be7cfeb587998934be9d9fee){.el}.
May use no more resources than the estimate reported by
[EstimateResources()](classtensorflow_1_1serving_1_1SimpleLoader.html#a05ede6c604d05037f59fe13472b48935){.el}.

If implementing
[Load()](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el},
you don\'t have to override
[LoadWithMetadata()](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24){.el}.

Reimplemented from
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}.
:::
:::

[]{#a4c9a2f88fd1cab8a68ffa69bb9900e24}

[[◆ ](#a4c9a2f88fd1cab8a68ffa69bb9900e24)]{.permalink}LoadWithMetadata() {#loadwithmetadata .memtitle}
------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename ServableType \>
:::

+-----------------------------------+-----------------------------------+
|   ----------                      | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------------- --- --- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------- ------------ --- -- |                                   |
|   Status [                        |                                   |
| tensorflow::serving::SimpleLoader |                                   |
| ](classtensorflow_1_1serving_1_1S |                                   |
| impleLoader.html){.el}\< Servable |                                   |
| Type \>::LoadWithMetadata   (   c |                                   |
| onst [Metadata](structtensorflow_ |                                   |
| 1_1serving_1_1Loader_1_1Metadata. |                                   |
| html){.el} &    *metadata*   )    |                                   |
|   ----------                      |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------------- --- --- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------- ------------ --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Similar to the above method, but takes Metadata as a param, which may be
used by the loader implementation appropriately.

If you\'re overriding
[LoadWithMetadata()](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24){.el},
because you can use the metadata appropriately, you can skip overriding
[Load()](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el}.

Reimplemented from
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.el}.
:::
:::

[]{#a914a9107be7cfeb587998934be9d9fee}

[[◆ ](#a914a9107be7cfeb587998934be9d9fee)]{.permalink}servable() {#servable .memtitle}
----------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename ServableType \>
:::

+-----------------------------------+-----------------------------------+
|   -------------------------       | [[inline]{.mlabel}[override]{.mla |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
|   [AnyPtr](classtensorflo         |                                   |
| w_1_1serving_1_1AnyPtr.html){.el} |                                   |
|  [tensorflow::serving::SimpleLoad |                                   |
| er](classtensorflow_1_1serving_1_ |                                   |
| 1SimpleLoader.html){.el}\< Servab |                                   |
| leType \>::servable   (      )    |                                   |
|   -------------------------       |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Returns an opaque interface to the underlying servable object. The
caller should know the precise type of the interface in order to make
actual use of it. For example:

CustomLoader implementation:

``` {.fragment}
class CustomLoader : public Loader {
 public:
  ...
  Status Load() override {
    servable_ = ...;
  }

  AnyPtr servable() override { return servable_; }

 private:
  CustomServable* servable_ = nullptr;
};
```

Serving user request:

``` {.fragment}
ServableHandle&lt;CustomServable> handle = ...
CustomServable* servable = handle.get();
servable->...
```

If
[servable()](classtensorflow_1_1serving_1_1SimpleLoader.html#a914a9107be7cfeb587998934be9d9fee){.el}
is called after successful
[Load()](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el}
and before
[Unload()](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.el},
it returns a valid, non-null
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el} object. If
called before a successful
[Load()](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el}
call or after
[Unload()](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.el},
it returns null
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el}.

Implements
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.el}.
:::
:::

[]{#ae24b904b3155f039fadd88b1c23e2f82}

[[◆ ](#ae24b904b3155f039fadd88b1c23e2f82)]{.permalink}Unload() {#unload .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename ServableType \>
:::

+-----------------------------------+-----------------------------------+
|   ----                            | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
|   vo                              |                                   |
| id [tensorflow::serving::SimpleLo |                                   |
| ader](classtensorflow_1_1serving_ |                                   |
| 1_1SimpleLoader.html){.el}\< Serv |                                   |
| ableType \>::Unload   (      )    |                                   |
|   ----                            |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Frees any resources allocated during
[Load()](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el}
(except perhaps for resources shared across servables that are still
needed for other active ones). The loader does not need to return to the
\"new\" state (i.e.
[Load()](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el}
cannot be called after
[Unload()](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.el}).

Implements
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/core/[simple\_loader.h](simple__loader_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
