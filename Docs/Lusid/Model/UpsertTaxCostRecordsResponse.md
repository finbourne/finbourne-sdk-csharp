# Finbourne.Sdk.Lusid.Model.UpsertTaxCostRecordsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Successes** | [Dictionary&lt;string, TaxCostRecord&gt;](TaxCostRecord.md) | Optional | The Tax Cost Records that were successfully upserted, keyed by the code supplied in the request. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The Tax Cost Records that failed to upsert, keyed by the code supplied in the request, with the reason for each failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertTaxCostRecordsResponse(
    successes: new TaxCostRecord(...),  // optional — The Tax Cost Records that were successfully upserted, keyed by the code supplied in the request.
    failed: new ErrorDetail(...),  // optional — The Tax Cost Records that failed to upsert, keyed by the code supplied in the request, with the reason for each failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertTaxCostRecordsResponse>(json);
```


## Related Models

- [TaxCostRecord](TaxCostRecord.md) — used in `Successes`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

