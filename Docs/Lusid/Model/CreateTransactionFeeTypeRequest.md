# Finbourne.Sdk.Lusid.Model.CreateTransactionFeeTypeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The display name of the transaction fee type. |
| **Description** | **string** | Optional | A description of the transaction fee type. |
| **Calculation** | [FeeCalculationRequest](FeeCalculationRequest.md) | Required | *No description available.* |
| **Condition** | **string** | Required | The condition that the transaction must meet in order for the fee to be applied. |
| **TxnPropertyKey** | **string** | Required | The property key to which the fee value will be applied and decorated onto the transaction. Must be in the &#39;Transaction&#39; property domain. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the transaction fee type. |
| **IsActive** | **bool** | Optional | Indicates whether the transaction fee type is currently active and should be applied to transactions. Optional when creating a transaction fee type, defaults to true, if a value is not provided. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateTransactionFeeTypeRequest(
    displayName: "...",  // required — The display name of the transaction fee type.
    description: "...",  // optional — A description of the transaction fee type.
    calculation: new FeeCalculationRequest(...),  // required
    condition: "...",  // required — The condition that the transaction must meet in order for the fee to be applied.
    txnPropertyKey: "...",  // required — The property key to which the fee value will be applied and decorated onto the transaction. Must be in the &#39;Transaction&#39; property domain.
    properties: new Property(...),  // optional — A set of properties for the transaction fee type.
    isActive: true  // optional — Indicates whether the transaction fee type is currently active and should be applied to transactions. Optional when creating a transaction fee type, defaults to true, if a value is not provided.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateTransactionFeeTypeRequest>(json);
```

- [FeeCalculationRequest](FeeCalculationRequest.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

