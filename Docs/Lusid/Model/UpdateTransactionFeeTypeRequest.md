# Finbourne.Sdk.Lusid.Model.UpdateTransactionFeeTypeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Optional | A description of the transaction fee type. |
| **Calculation** | [FeeCalculationRequest](FeeCalculationRequest.md) | Optional | *No description available.* |
| **Condition** | **string** | Optional | The condition that the transaction must meet in order for the fee to be applied. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the transaction fee type. |
| **IsActive** | **bool?** | Optional | Indicates whether the transaction fee type is currently active and should be applied to transactions. Optional when creating a transaction fee type, defaults to true, if a value is not provided. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateTransactionFeeTypeRequest(
    description: "...",  // optional — A description of the transaction fee type.
    calculation: new FeeCalculationRequest(...),  // optional
    condition: "...",  // optional — The condition that the transaction must meet in order for the fee to be applied.
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
var instance = JsonConvert.DeserializeObject<UpdateTransactionFeeTypeRequest>(json);
```

- [FeeCalculationRequest](FeeCalculationRequest.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

