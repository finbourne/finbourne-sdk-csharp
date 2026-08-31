# Finbourne.Sdk.Lusid.Model.CreateTransferResponse

The transfer that was created, and the transaction legs it booked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransferId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransferType** | **string** | Optional | *No description available.* |
| **PortfolioIdOut** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioIdIn** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransactionIdOut** | **string** | Optional | *No description available.* |
| **TransactionIdIn** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateTransferResponse(
    transferId: new ResourceId(...),  // optional
    transferType: "...",  // optional
    portfolioIdOut: new ResourceId(...),  // optional
    portfolioIdIn: new ResourceId(...),  // optional
    transactionIdOut: "...",  // optional
    transactionIdIn: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateTransferResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

