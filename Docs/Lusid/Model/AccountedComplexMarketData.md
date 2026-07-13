# Finbourne.Sdk.Lusid.Model.AccountedComplexMarketData

The Valuation Point complex market data response for a Fund, including the origin of the complex market data relative to the Valuation Point period.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComplexMarketData** | [ComplexMarketData](ComplexMarketData.md) | Optional | *No description available.* |
| **ValuationPointOrigin** | **string** | Optional | Designates if the complex market data was originally part of the Valuation Point or if it was added as part of a Complex Close action. Available values: None, Original, Added, OriginalAndAdded. |
| **AddedOriginValuationPointCode** | **string** | Optional | The Valuation Point code, only for complex market data added as part of a Complex Close action. |
| **AddedOriginValuationPointVariantCode** | **string** | Optional | The Valuation Point variant code, only for complex market data added as part of a Complex Close action. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AccountedComplexMarketData(
    complexMarketData: new ComplexMarketData(...),  // optional
    valuationPointOrigin: "...",  // optional — Designates if the complex market data was originally part of the Valuation Point or if it was added as part of a Complex Close action. Available values: None, Original, Added, OriginalAndAdded.
    addedOriginValuationPointCode: "...",  // optional — The Valuation Point code, only for complex market data added as part of a Complex Close action.
    addedOriginValuationPointVariantCode: "..."  // optional — The Valuation Point variant code, only for complex market data added as part of a Complex Close action.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccountedComplexMarketData>(json);
```


## Related Models

- [ComplexMarketData](ComplexMarketData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

