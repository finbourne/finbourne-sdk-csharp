# Finbourne.Sdk.Lusid.Model.ListComplexMarketDataWithMetaDataResponse

Wraps a ComplexMarketData object with information that was retrieved from storage with it.  In particular,  the scope that the data was stored in,  and an object identifying the market data in that scope.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Optional | The scope that the listed ComplexMarketData entity is stored in. |
| **MarketDataId** | [ComplexMarketDataId](ComplexMarketDataId.md) | Optional | *No description available.* |
| **MarketData** | [ComplexMarketData](ComplexMarketData.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ListComplexMarketDataWithMetaDataResponse(
    scope: "...",  // optional — The scope that the listed ComplexMarketData entity is stored in.
    marketDataId: new ComplexMarketDataId(...),  // optional
    marketData: new ComplexMarketData(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ListComplexMarketDataWithMetaDataResponse>(json);
```

- [ComplexMarketDataId](ComplexMarketDataId.md)
- [ComplexMarketData](ComplexMarketData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

