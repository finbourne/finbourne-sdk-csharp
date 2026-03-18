# Finbourne.Sdk.Lusid.Model.DecimalList

> **Inherits from:** [ReferenceList](ReferenceList.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | **List&lt;decimal&gt;** | Required | *No description available.* |
| **ReferenceListType** | **string** | Required | The reference list values. The available values are: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList Default: `ReferenceListTypeEnum.DecimalList` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DecimalList(
    values: ,  // required
    referenceListType: "..."  // required — The reference list values. The available values are: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DecimalList>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

