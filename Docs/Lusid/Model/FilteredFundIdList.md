# Finbourne.Sdk.Lusid.Model.FilteredFundIdList

> **Inherits from:** [ReferenceList](ReferenceList.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Filter** | **string** | Required | *No description available.* |
| **Values** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | *No description available.* *(read-only)* |
| **ReferenceListType** | **string** | Required | The reference list values. Available values: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList, FilteredFundIdList. Default: `ReferenceListTypeEnum.FilteredFundIdList` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FilteredFundIdList(
    filter: "...",  // required
    values: new List<ResourceId>(),  // optional
    referenceListType: "..."  // required — The reference list values. Available values: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList, FilteredFundIdList.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FilteredFundIdList>(json);
```


- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

