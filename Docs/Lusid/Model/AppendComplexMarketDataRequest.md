# Finbourne.Sdk.Lusid.Model.AppendComplexMarketDataRequest

The details of the point to be appended to a complex market data item.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MarketDataId** | [ComplexMarketDataId](ComplexMarketDataId.md) | Required | *No description available.* |
| **AppendMarketData** | [AppendMarketData](AppendMarketData.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AppendComplexMarketDataRequest(
    marketDataId: new ComplexMarketDataId(...),  // required
    appendMarketData: new AppendMarketData(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AppendComplexMarketDataRequest>(json);
```


## Related Models

- [ComplexMarketDataId](ComplexMarketDataId.md)
- [AppendMarketData](AppendMarketData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

