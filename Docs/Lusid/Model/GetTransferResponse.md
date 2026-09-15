# Finbourne.Sdk.Lusid.Model.GetTransferResponse

A transfer and both of the transactions it booked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransferId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransferType** | **string** | Optional | *No description available.* |
| **PortfolioIdOut** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioIdIn** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransactionOut** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **TransactionIn** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetTransferResponse(
    transferId: new ResourceId(...),  // optional
    transferType: "...",  // optional
    portfolioIdOut: new ResourceId(...),  // optional
    portfolioIdIn: new ResourceId(...),  // optional
    transactionOut: new Transaction(...),  // optional
    transactionIn: new Transaction(...),  // optional
    properties: new Property(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetTransferResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Transaction](Transaction.md)
- [Transaction](Transaction.md)
- [Property](Property.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

