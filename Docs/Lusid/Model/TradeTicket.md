# Finbourne.Sdk.Lusid.Model.TradeTicket

The base class for representing a Trade Ticket in LUSID.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TradeTicketType** | **string** | Required | The available values are: LusidTradeTicket, ExternalTradeTicket |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TradeTicket(
    tradeTicketType: "..."  // required — The available values are: LusidTradeTicket, ExternalTradeTicket
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TradeTicket>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

