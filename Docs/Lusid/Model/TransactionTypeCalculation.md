# Finbourne.Sdk.Lusid.Model.TransactionTypeCalculation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of calculation to perform |
| **Side** | **string** | Optional | The side to which the calculation is applied |
| **Formula** | **string** | Optional | The formula used to derive the total consideration amount when it is not provided on the transaction |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionTypeCalculation(
    type: "...",  // required — The type of calculation to perform
    side: "...",  // optional — The side to which the calculation is applied
    formula: "..."  // optional — The formula used to derive the total consideration amount when it is not provided on the transaction
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionTypeCalculation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

