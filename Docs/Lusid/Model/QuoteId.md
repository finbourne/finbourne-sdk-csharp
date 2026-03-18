# Finbourne.Sdk.Lusid.Model.QuoteId

The unique identifier of the quote.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **QuoteSeriesId** | [QuoteSeriesId](QuoteSeriesId.md) | Required | *No description available.* |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The effective datetime or cut label at which the quote is valid from. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QuoteId(
    quoteSeriesId: new QuoteSeriesId(...),  // required
    effectiveAt: new DateTimeOrCutLabel(...)  // required — The effective datetime or cut label at which the quote is valid from.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QuoteId>(json);
```


## Related Models

- [QuoteSeriesId](QuoteSeriesId.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

