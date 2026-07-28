# Finbourne.Sdk.Lusid.Model.PaymentRecordReference

Identifies a Payment Record attached to a specific transaction within a portfolio.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TransactionId** | **string** | Required | The ID of the cash transaction within the portfolio to which the Payment Record is attached. |
| **PaymentRecordId** | **string** | Required | The unique identifier of the Payment Record attached to the above transaction. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentRecordReference(
    portfolioId: new ResourceId(...),  // required
    transactionId: "...",  // required — The ID of the cash transaction within the portfolio to which the Payment Record is attached.
    paymentRecordId: "..."  // required — The unique identifier of the Payment Record attached to the above transaction.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentRecordReference>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

