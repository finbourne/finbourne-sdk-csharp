# Finbourne.Sdk.Lusid.Model.TransferAgencyOrderToEstimate

The values of an order to estimate, for an order that has not been saved yet or whose values are being  changed. Carries only what the estimate reads - it is not a whole order and cannot be used to create one.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstrumentIdentifierType** | **string** | Required | *No description available.* |
| **InstrumentIdentifier** | **string** | Required | *No description available.* |
| **InstrumentScope** | **string** | Optional | *No description available.* |
| **TransactionCategory** | **string** | Optional | Available values: Subscription, Redemption, SwitchOut, SwitchIn, TransferOut, TransferIn. |
| **Currency** | **string** | Required | *No description available.* |
| **Quantity** | **decimal?** | Optional | *No description available.* |
| **Amount** | **decimal?** | Optional | *No description available.* |
| **Weight** | **decimal?** | Optional | *No description available.* |
| **TransactionDate** | **DateTimeOffset?** | Optional | *No description available.* |
| **ExchangeRate** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransferAgencyOrderToEstimate(
    portfolioId: new ResourceId(...),  // required
    instrumentIdentifierType: "...",  // required
    instrumentIdentifier: "...",  // required
    instrumentScope: "...",  // optional
    transactionCategory: "...",  // optional — Available values: Subscription, Redemption, SwitchOut, SwitchIn, TransferOut, TransferIn.
    currency: "...",  // required
    quantity: 0.0d,  // optional
    amount: 0.0d,  // optional
    weight: 0.0d,  // optional
    transactionDate: DateTimeOffset.Now,  // optional
    exchangeRate: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransferAgencyOrderToEstimate>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

