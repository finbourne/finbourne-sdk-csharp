# Finbourne.Sdk.Lusid.Model.Quote

The quote id, value and lineage of the quotes all keyed by a unique correlation id.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **QuoteId** | [QuoteId](QuoteId.md) | Required | *No description available.* |
| **MetricValue** | [MetricValue](MetricValue.md) | Optional | *No description available.* |
| **Lineage** | **string** | Optional | Description of the quote&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **CutLabel** | **string** | Optional | The cut label that this quote was updated or inserted with. |
| **UploadedBy** | **string** | Required | The unique id of the user that updated or inserted the quote. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime at which the quote was committed to LUSID. |
| **ScaleFactor** | **decimal?** | Optional | An optional scale factor for non-standard scaling of quotes against the instrument. For example, if you wish the quote&#39;s Value to be scaled down by a factor of 100, enter 100. If not supplied, the default ScaleFactor is 1. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Quote(
    quoteId: new QuoteId(...),  // required
    metricValue: new MetricValue(...),  // optional
    lineage: "...",  // optional — Description of the quote&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;.
    cutLabel: "...",  // optional — The cut label that this quote was updated or inserted with.
    uploadedBy: "...",  // required — The unique id of the user that updated or inserted the quote.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime at which the quote was committed to LUSID.
    scaleFactor: 0.0d  // optional — An optional scale factor for non-standard scaling of quotes against the instrument. For example, if you wish the quote&#39;s Value to be scaled down by a factor of 100, enter 100. If not supplied, the default ScaleFactor is 1.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Quote>(json);
```


## Related Models

- [QuoteId](QuoteId.md)
- [MetricValue](MetricValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

