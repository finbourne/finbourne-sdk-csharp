# Finbourne.Sdk.Lusid.Model.PaymentInstructionRequest

A request to create or update a Payment Instruction. Status is not accepted here —  status transitions are managed exclusively via the dedicated Payment Instruction status API.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PaymentRecordIds** | [List&lt;PaymentRecordReference&gt;](PaymentRecordReference.md) | Required | One or more Payment Records batched into this instruction block. All referenced Payment Records must share the same currency as the top-level currency field. |
| **Currency** | **string** | Required | ISO 4217 currency code. All referenced Payment Records must share this currency value. |
| **TotalPaymentAmount** | **decimal** | Required | Total payment amount across all referenced Payment Records. |
| **PaymentDate** | **DateTimeOffset** | Required | The value date on which settlement is due. ISO 8601 date. |
| **PayorPaymentDetailsReference** | [PaymentDetailsReference](PaymentDetailsReference.md) | Required | *No description available.* |
| **PayeePaymentDetailsReference** | [PaymentDetailsReference](PaymentDetailsReference.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this Payment Instruction. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentInstructionRequest(
    id: new ResourceId(...),  // required
    paymentRecordIds: new List<PaymentRecordReference>(),  // required — One or more Payment Records batched into this instruction block. All referenced Payment Records must share the same currency as the top-level currency field.
    currency: "...",  // required — ISO 4217 currency code. All referenced Payment Records must share this currency value.
    totalPaymentAmount: 0.0d,  // required — Total payment amount across all referenced Payment Records.
    paymentDate: DateTimeOffset.Now,  // required — The value date on which settlement is due. ISO 8601 date.
    payorPaymentDetailsReference: new PaymentDetailsReference(...),  // required
    payeePaymentDetailsReference: new PaymentDetailsReference(...),  // required
    properties: new PerpetualProperty(...)  // optional — Client-defined properties associated with this Payment Instruction.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentInstructionRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PaymentRecordReference](PaymentRecordReference.md) — used in `PaymentRecordIds`
- [PaymentDetailsReference](PaymentDetailsReference.md)
- [PaymentDetailsReference](PaymentDetailsReference.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

