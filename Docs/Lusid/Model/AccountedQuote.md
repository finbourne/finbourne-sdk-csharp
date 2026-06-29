# Finbourne.Sdk.Lusid.Model.AccountedQuote

The Valuation Point quote response for a Fund, including the origin of the quote relative to the Valuation Point period.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quote** | [Quote](Quote.md) | Optional | *No description available.* |
| **ValuationPointOrigin** | **string** | Optional | Designates if the quote was originally part of the Valuation Point or if it was added as part of a Complex Close action. Available values: None, Original, Added, OriginalAndAdded. |
| **AddedOriginValuationPointCode** | **string** | Optional | The Valuation Point code, only for quotes added as part of a Complex Close action. |
| **AddedOriginValuationPointVariantCode** | **string** | Optional | The Valuation Point variant code, only for quotes added as part of a Complex Close action. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AccountedQuote(
    quote: new Quote(...),  // optional
    valuationPointOrigin: "...",  // optional — Designates if the quote was originally part of the Valuation Point or if it was added as part of a Complex Close action. Available values: None, Original, Added, OriginalAndAdded.
    addedOriginValuationPointCode: "...",  // optional — The Valuation Point code, only for quotes added as part of a Complex Close action.
    addedOriginValuationPointVariantCode: "..."  // optional — The Valuation Point variant code, only for quotes added as part of a Complex Close action.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccountedQuote>(json);
```


## Related Models

- [Quote](Quote.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

