# Finbourne.Sdk.Lusid.Model.TransitionPaymentInstructionsResponse

The response from transitioning the status of a set of Payment Instructions. Each request key from the  incoming map appears in exactly one of Values or Failed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, PaymentInstruction&gt;](PaymentInstruction.md) | Optional | The Payment Instructions that were transitioned successfully, at their new status, keyed by the ephemeral request key supplied by the caller. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | Details of the requested transitions that failed, keyed by the ephemeral request key supplied by the caller. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransitionPaymentInstructionsResponse(
    values: new PaymentInstruction(...),  // optional — The Payment Instructions that were transitioned successfully, at their new status, keyed by the ephemeral request key supplied by the caller.
    failed: new ErrorDetail(...),  // optional — Details of the requested transitions that failed, keyed by the ephemeral request key supplied by the caller.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransitionPaymentInstructionsResponse>(json);
```


## Related Models

- [PaymentInstruction](PaymentInstruction.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

