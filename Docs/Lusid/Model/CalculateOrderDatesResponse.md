# Finbourne.Sdk.Lusid.Model.CalculateOrderDatesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Successes** | [Dictionary&lt;string, TransferAgencyDates&gt;](TransferAgencyDates.md) | Optional | A dictionary of successful date calculations, keyed by the request key. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | A dictionary of failed date calculations, keyed by the request key, containing the error details of any failures that occurred during the calculation. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CalculateOrderDatesResponse(
    successes: new TransferAgencyDates(...),  // optional — A dictionary of successful date calculations, keyed by the request key.
    failed: new ErrorDetail(...),  // optional — A dictionary of failed date calculations, keyed by the request key, containing the error details of any failures that occurred during the calculation.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CalculateOrderDatesResponse>(json);
```


## Related Models

- [TransferAgencyDates](TransferAgencyDates.md) — used in `Successes`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

