# Finbourne.Sdk.Lusid.Model.IndexModelOptions

> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioScaling** | **string** | Required | Available values: Sum, AbsoluteSum, Unity. |
| **LookthroughPortfolioRelationshipId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ModelOptionsType** | **string** | Required | Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions. Default: `ModelOptionsTypeEnum.IndexModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IndexModelOptions(
    portfolioScaling: "...",  // required — Available values: Sum, AbsoluteSum, Unity.
    lookthroughPortfolioRelationshipId: new ResourceId(...),  // optional
    modelOptionsType: "..."  // required — Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IndexModelOptions>(json);
```


- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

