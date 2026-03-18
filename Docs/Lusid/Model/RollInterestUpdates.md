# Finbourne.Sdk.Lusid.Model.RollInterestUpdates

Describes changes to the interest of a FlexibleDeposit instrument as the result of a DepositRollEvent.  Both the interest to be withdrawn and the interest to be reinvested must be specified (either as an amount or as a percentage).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WithdrawInterestAmount** | **decimal?** | Optional | The amount of interest that should be withdrawn from a FlexibleDeposit as the result of a roll event. |
| **WithdrawInterestPercentage** | **decimal?** | Optional | The percentage of interest that should be withdrawn from a FlexibleDeposit instrument as the result of a roll event. |
| **ReinvestInterestAmount** | **decimal?** | Optional | The amount of interest that should be reinvested in a FlexibleDeposit instrument as the result of a roll event. |
| **ReinvestInterestPercentage** | **decimal?** | Optional | The percentage of interest that should be reinvested in a FlexibleDeposit instrument as the result of a roll event. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RollInterestUpdates(
    withdrawInterestAmount: 0.0d,  // optional — The amount of interest that should be withdrawn from a FlexibleDeposit as the result of a roll event.
    withdrawInterestPercentage: 0.0d,  // optional — The percentage of interest that should be withdrawn from a FlexibleDeposit instrument as the result of a roll event.
    reinvestInterestAmount: 0.0d,  // optional — The amount of interest that should be reinvested in a FlexibleDeposit instrument as the result of a roll event.
    reinvestInterestPercentage: 0.0d  // optional — The percentage of interest that should be reinvested in a FlexibleDeposit instrument as the result of a roll event.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RollInterestUpdates>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

