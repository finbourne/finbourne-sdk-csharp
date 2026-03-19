# Finbourne.Sdk.Lusid.Model.UpdateTransactionFeeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Optional | A description of the transaction fee. |
| **Calculation** | [FeeCalculationRequest](FeeCalculationRequest.md) | Optional | *No description available.* |
| **Condition** | **string** | Optional | The condition that the transaction must meet in order for the fee to be applied. |
| **TxnPropertyKey** | **string** | Optional | The property key to which the fee value will be applied and decorated onto the transaction. Must be in the &#39;Transaction&#39; property domain. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the transaction fee. |
| **IsActive** | **bool?** | Optional | Indicates whether the transaction fee is currently active and should be applied to transactions. Optional when creating a transaction fee, defaults to true, if a value is not provided. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateTransactionFeeRequest(
    description: "...",  // optional — A description of the transaction fee.
    calculation: new FeeCalculationRequest(...),  // optional
    condition: "...",  // optional — The condition that the transaction must meet in order for the fee to be applied.
    txnPropertyKey: "...",  // optional — The property key to which the fee value will be applied and decorated onto the transaction. Must be in the &#39;Transaction&#39; property domain.
    properties: new Property(...),  // optional — A set of properties for the transaction fee.
    isActive: true  // optional — Indicates whether the transaction fee is currently active and should be applied to transactions. Optional when creating a transaction fee, defaults to true, if a value is not provided.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateTransactionFeeRequest>(json);
```

- [FeeCalculationRequest](FeeCalculationRequest.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

