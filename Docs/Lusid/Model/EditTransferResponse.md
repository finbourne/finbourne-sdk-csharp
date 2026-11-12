# Finbourne.Sdk.Lusid.Model.EditTransferResponse

The identity of an edited transfer and of the two transaction legs it rebooked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransferId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransferType** | **string** | Optional | The derived type of the transfer: &#39;Transfer&#39; when the position moves between portfolios, &#39;Switch&#39; when one instrument is exchanged for another within a portfolio, and &#39;Twitch&#39; when the position moves between portfolios and changes instrument at the same time. |
| **PortfolioIdOut** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioIdIn** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransactionIdOut** | **string** | Optional | The transaction id of the rebooked outgoing leg. |
| **TransactionIdIn** | **string** | Optional | The transaction id of the rebooked incoming leg. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EditTransferResponse(
    transferId: new ResourceId(...),  // optional
    transferType: "...",  // optional — The derived type of the transfer: &#39;Transfer&#39; when the position moves between portfolios, &#39;Switch&#39; when one instrument is exchanged for another within a portfolio, and &#39;Twitch&#39; when the position moves between portfolios and changes instrument at the same time.
    portfolioIdOut: new ResourceId(...),  // optional
    portfolioIdIn: new ResourceId(...),  // optional
    transactionIdOut: "...",  // optional — The transaction id of the rebooked outgoing leg.
    transactionIdIn: "..."  // optional — The transaction id of the rebooked incoming leg.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EditTransferResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

