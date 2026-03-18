# Finbourne.Sdk.Lusid.Model.UpsertQuoteRequest

The details of the quote including its unique identifier, value and lineage.  Please note the Unit field on MetricValue is nullable on the upsert but there  is validation within the quote store to make sure this field is populated.  In the absence of a real unit then we recommend putting something in line with  the data in QuoteId.QuoteSeriesId.quoteType e.g. InterestRate.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **QuoteId** | [QuoteId](QuoteId.md) | Required | *No description available.* |
| **MetricValue** | [MetricValue](MetricValue.md) | Optional | *No description available.* |
| **Lineage** | **string** | Optional | Description of the quote&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **ScaleFactor** | **decimal?** | Optional | An optional scale factor for non-standard scaling of quotes against the instrument. For example, if you wish the quote&#39;s Value to be scaled down by a factor of 100, enter 100. If not supplied, the default ScaleFactor is 1. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertQuoteRequest(
    quoteId: new QuoteId(...),  // required
    metricValue: new MetricValue(...),  // optional
    lineage: "...",  // optional — Description of the quote&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;.
    scaleFactor: 0.0d  // optional — An optional scale factor for non-standard scaling of quotes against the instrument. For example, if you wish the quote&#39;s Value to be scaled down by a factor of 100, enter 100. If not supplied, the default ScaleFactor is 1.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertQuoteRequest>(json);
```


## Related Models

- [QuoteId](QuoteId.md)
- [MetricValue](MetricValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

