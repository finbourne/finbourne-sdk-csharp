# Finbourne.Sdk.Lusid.Model.UpsertComplexMarketDataRequest

The details of the complex market data item to upsert into Lusid.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MarketDataId** | [ComplexMarketDataId](ComplexMarketDataId.md) | Required | *No description available.* |
| **MarketData** | [ComplexMarketData](ComplexMarketData.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertComplexMarketDataRequest(
    marketDataId: new ComplexMarketDataId(...),  // required
    marketData: new ComplexMarketData(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertComplexMarketDataRequest>(json);
```


## Related Models

- [ComplexMarketDataId](ComplexMarketDataId.md)
- [ComplexMarketData](ComplexMarketData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

