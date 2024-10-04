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
-   [ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tensorflow::serving::ResourceUtil Member List
:::
:::
:::

::: {.contents}
This is the complete list of members for
[tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el},
including all inherited members.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------- ---------------------
  **Add**(const ResourceAllocation &to\_add, ResourceAllocation \*base) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                          [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **CreateBoundResource**(const string &device, const string &kind, uint32 device\_instance=0) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                   [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **Equal**(const ResourceAllocation &lhs, const ResourceAllocation &rhs) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                        [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **GetQuantity**(const Resource &resource, const ResourceAllocation &allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **IsBound**(const ResourceAllocation &allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                              [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **IsNormalized**(const ResourceAllocation &allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                         [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   [virtual]{.mlabel}
  **LessThanOrEqual**(const ResourceAllocation &lhs, const ResourceAllocation &rhs) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                              [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **Max**(const ResourceAllocation &lhs, const ResourceAllocation &rhs) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                          [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **Min**(const ResourceAllocation &lhs, const ResourceAllocation &rhs) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                          [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **Multiply**(uint64\_t multiplier, ResourceAllocation \*base) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                  [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **Normalize**(const ResourceAllocation &allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                            [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   [virtual]{.mlabel}
  **NormalizeResourceAllocation**(const ResourceAllocation &allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                          [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **Overbind**(const ResourceAllocation &allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                             [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **ResourcesEqual**(const Resource &lhs, const Resource &rhs) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                   [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **ResourceUtil**(const Options &options) (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                                             [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   [explicit]{.mlabel}
  **SetQuantity**(const Resource &resource, uint64\_t quantity, ResourceAllocation \*allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                 [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **Subtract**(const ResourceAllocation &to\_subtract, ResourceAllocation \*base) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **VerifyOverrideDeviceValidity**(const ResourceAllocation &base\_allocation, const ResourceAllocation &override\_allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})   [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **VerifyResourceValidity**(const Resource &resource) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                           [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   
  **VerifyValidity**(const ResourceAllocation &allocation) const (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                       [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   [virtual]{.mlabel}
  **\~ResourceUtil**()=default (defined in [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el})                                                                                                         [tensorflow::serving::ResourceUtil](classtensorflow_1_1serving_1_1ResourceUtil.html){.el}   [virtual]{.mlabel}
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------- ---------------------
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
