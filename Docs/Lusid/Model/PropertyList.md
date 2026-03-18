# Finbourne.Sdk.Lusid.Model.PropertyList

> **Inherits from:** [ReferenceList](ReferenceList.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;Property&gt;](Property.md) | Required | *No description available.* |
| **ReferenceListType** | **string** | Required | The reference list values. The available values are: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList Default: `ReferenceListTypeEnum.PropertyList` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyList(
    values: new List<Property>(),  // required
    referenceListType: "..."  // required — The reference list values. The available values are: PortfolioGroupIdList, PortfolioIdList, AddressKeyList, StringList, InstrumentList, DecimalList, PropertyList, FundIdList
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyList>(json);
```



- [Property](Property.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

