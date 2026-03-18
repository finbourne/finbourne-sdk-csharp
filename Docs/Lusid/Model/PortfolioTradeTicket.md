# Finbourne.Sdk.Lusid.Model.PortfolioTradeTicket

Response for querying trade tickets
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourcePortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TradeTicket** | [LusidTradeTicket](LusidTradeTicket.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioTradeTicket(
    sourcePortfolioId: new ResourceId(...),  // optional
    tradeTicket: new LusidTradeTicket(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioTradeTicket>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [LusidTradeTicket](LusidTradeTicket.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

