# Finbourne.Sdk.Lusid.Model.PaymentInstruction

A Payment Instruction groups one or more Payment Records into a single block  for transmission to a downstream treasury management system via the Horizon integration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PaymentRecordIds** | [List&lt;PaymentRecordReference&gt;](PaymentRecordReference.md) | Required | One or more Payment Records batched into this instruction block. All referenced Payment Records must share the same currency as the top-level currency field. |
| **Currency** | **string** | Required | ISO 4217 currency code. All referenced Payment Records must share this currency value. |
| **TotalPaymentAmount** | **decimal** | Required | Total payment amount across all referenced Payment Records. |
| **PaymentDate** | **DateTimeOffset** | Required | The value date on which settlement is due. ISO 8601 date. |
| **PayorPaymentDetailsReference** | [PaymentDetailsReferenceResponse](PaymentDetailsReferenceResponse.md) | Required | *No description available.* |
| **PayeePaymentDetailsReference** | [PaymentDetailsReferenceResponse](PaymentDetailsReferenceResponse.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this Payment Instruction. |
| **Status** | [PaymentInstructionStatus](PaymentInstructionStatus.md) | Required | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentInstruction(
    id: new ResourceId(...),  // required
    paymentRecordIds: new List<PaymentRecordReference>(),  // required — One or more Payment Records batched into this instruction block. All referenced Payment Records must share the same currency as the top-level currency field.
    currency: "...",  // required — ISO 4217 currency code. All referenced Payment Records must share this currency value.
    totalPaymentAmount: 0.0d,  // required — Total payment amount across all referenced Payment Records.
    paymentDate: DateTimeOffset.Now,  // required — The value date on which settlement is due. ISO 8601 date.
    payorPaymentDetailsReference: new PaymentDetailsReferenceResponse(...),  // required
    payeePaymentDetailsReference: new PaymentDetailsReferenceResponse(...),  // required
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this Payment Instruction.
    status: new PaymentInstructionStatus(...),  // required
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentInstruction>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PaymentRecordReference](PaymentRecordReference.md) — used in `PaymentRecordIds`
- [PaymentDetailsReferenceResponse](PaymentDetailsReferenceResponse.md)
- [PaymentDetailsReferenceResponse](PaymentDetailsReferenceResponse.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [PaymentInstructionStatus](PaymentInstructionStatus.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

