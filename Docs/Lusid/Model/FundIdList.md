# Finbourne.Sdk.Lusid.Model.FundIdList

> **Inherits from:** [ReferenceList](ReferenceList.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |
| **NavTypeCodesHint** | **List&lt;string&gt;** | Optional | The NAV type codes this list nominates, in priority order; entries may contain &#39;*&#39; wildcards.  For each fund the first matching code the fund defines is picked, falling back to the fund&#39;s  primary (official) NAV type when the list is empty or nothing matches. Optional. |
| **ReferenceListType** | **string** | Required | The reference list values. Available values: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList, FilteredFundIdList. Default: `ReferenceListTypeEnum.FundIdList` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundIdList(
    values: new List<ResourceId>(),  // required
    navTypeCodesHint: ,  // optional — The NAV type codes this list nominates, in priority order; entries may contain &#39;*&#39; wildcards.  For each fund the first matching code the fund defines is picked, falling back to the fund&#39;s  primary (official) NAV type when the list is empty or nothing matches. Optional.
    referenceListType: "..."  // required — The reference list values. Available values: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList, FilteredFundIdList.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundIdList>(json);
```



- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

