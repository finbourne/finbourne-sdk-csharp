# Finbourne.Sdk.Lusid.Model.ExternalDealingEstimateLine

One order within an external order set: a share class, a direction and either a number of units or an amount.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifierType** | **string** | Required | *No description available.* |
| **InstrumentIdentifier** | **string** | Required | *No description available.* |
| **InstrumentScope** | **string** | Optional | *No description available.* |
| **TradeType** | **string** | Required | Available values: Subscription, Redemption, SwitchOut, SwitchIn, TransferOut, TransferIn. |
| **Units** | **decimal?** | Optional | *No description available.* |
| **Amount** | [ExternalDealingEstimateAmount](ExternalDealingEstimateAmount.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExternalDealingEstimateLine(
    instrumentIdentifierType: "...",  // required
    instrumentIdentifier: "...",  // required
    instrumentScope: "...",  // optional
    tradeType: "...",  // required — Available values: Subscription, Redemption, SwitchOut, SwitchIn, TransferOut, TransferIn.
    units: 0.0d,  // optional
    amount: new ExternalDealingEstimateAmount(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalDealingEstimateLine>(json);
```

- [ExternalDealingEstimateAmount](ExternalDealingEstimateAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

