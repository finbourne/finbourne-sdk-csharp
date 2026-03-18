# Finbourne.Sdk.Lusid.Model.RollPrincipalUpdates

Describes changes to the principal on a FlexibleDeposit instrument as the result of a DepositRollEvent.  Either the principal to be withdrawn or the principal increase must be specified (either as an amount or a percentage).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WithdrawPrincipalAmount** | **decimal?** | Optional | The amount of principal that should be withdrawn from the FlexibleDeposit. |
| **WithdrawPrincipalPercentage** | **decimal?** | Optional | The percentage of principal that should be withdrawn from the FlexibleDeposit. |
| **IncreasePrincipalAmount** | **decimal?** | Optional | The amount of principal that should be added to the FlexibleDeposit. |
| **IncreasePrincipalPercentage** | **decimal?** | Optional | The percentage of principal that should be added to the FlexibleDeposit. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RollPrincipalUpdates(
    withdrawPrincipalAmount: 0.0d,  // optional — The amount of principal that should be withdrawn from the FlexibleDeposit.
    withdrawPrincipalPercentage: 0.0d,  // optional — The percentage of principal that should be withdrawn from the FlexibleDeposit.
    increasePrincipalAmount: 0.0d,  // optional — The amount of principal that should be added to the FlexibleDeposit.
    increasePrincipalPercentage: 0.0d  // optional — The percentage of principal that should be added to the FlexibleDeposit.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RollPrincipalUpdates>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

