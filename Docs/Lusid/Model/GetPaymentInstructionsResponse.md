# Finbourne.Sdk.Lusid.Model.GetPaymentInstructionsResponse

The response from getting Payment Instructions by payment record id. Each requested payment record id  appears in exactly one of Values or Failed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, PaymentInstruction&gt;](PaymentInstruction.md) | Optional | The Payment Instructions that were found, keyed by the payment record id used to retrieve them. Only Payment Instructions that were found will be contained in this collection. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The payment record ids that did not resolve to a Payment Instruction, along with the nature of the failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetPaymentInstructionsResponse(
    values: new PaymentInstruction(...),  // optional — The Payment Instructions that were found, keyed by the payment record id used to retrieve them. Only Payment Instructions that were found will be contained in this collection.
    failed: new ErrorDetail(...),  // optional — The payment record ids that did not resolve to a Payment Instruction, along with the nature of the failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetPaymentInstructionsResponse>(json);
```


## Related Models

- [PaymentInstruction](PaymentInstruction.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

