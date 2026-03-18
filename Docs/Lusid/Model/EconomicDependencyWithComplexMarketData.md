# Finbourne.Sdk.Lusid.Model.EconomicDependencyWithComplexMarketData

Container class pairing economic dependency and complex market data (i.e. discounting curves, etc.)
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EconomicDependency** | [EconomicDependency](EconomicDependency.md) | Required | *No description available.* |
| **ComplexMarketData** | [ComplexMarketData](ComplexMarketData.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EconomicDependencyWithComplexMarketData(
    economicDependency: new EconomicDependency(...),  // required
    complexMarketData: new ComplexMarketData(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EconomicDependencyWithComplexMarketData>(json);
```


## Related Models

- [EconomicDependency](EconomicDependency.md)
- [ComplexMarketData](ComplexMarketData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

