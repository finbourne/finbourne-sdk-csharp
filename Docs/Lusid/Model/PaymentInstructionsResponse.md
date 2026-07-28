# Finbourne.Sdk.Lusid.Model.PaymentInstructionsResponse

The response from upserting a set of Payment Instructions. Each request key from the  incoming map appears in exactly one of Successes or Failed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Successes** | [Dictionary&lt;string, PaymentInstruction&gt;](PaymentInstruction.md) | Optional | The Payment Instructions that were created or updated successfully, keyed by the ephemeral request key supplied by the caller. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | Details of the requests that failed, keyed by the ephemeral request key supplied by the caller. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentInstructionsResponse(
    successes: new PaymentInstruction(...),  // optional — The Payment Instructions that were created or updated successfully, keyed by the ephemeral request key supplied by the caller.
    failed: new ErrorDetail(...),  // optional — Details of the requests that failed, keyed by the ephemeral request key supplied by the caller.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentInstructionsResponse>(json);
```


## Related Models

- [PaymentInstruction](PaymentInstruction.md) — used in `Successes`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

