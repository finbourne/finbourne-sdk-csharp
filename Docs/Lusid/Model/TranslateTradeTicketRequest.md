# Finbourne.Sdk.Lusid.Model.TranslateTradeTicketRequest

A collection of instruments to translate, along with the target dialect to translate into.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Tickets** | [Dictionary&lt;string, TradeTicket&gt;](TradeTicket.md) | Required | The collection of trade tickets to translate.                Each trade ticket should be keyed by a unique correlation id. This id is ephemeral  and is not stored by LUSID. It serves only as a way to easily identify each instrument in the response. |
| **Dialect** | **string** | Required | The target dialect that the given instruments should be translated to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslateTradeTicketRequest(
    tickets: new TradeTicket(...),  // required — The collection of trade tickets to translate.                Each trade ticket should be keyed by a unique correlation id. This id is ephemeral  and is not stored by LUSID. It serves only as a way to easily identify each instrument in the response.
    dialect: "..."  // required — The target dialect that the given instruments should be translated to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslateTradeTicketRequest>(json);
```


## Related Models

- [TradeTicket](TradeTicket.md) — used in `Tickets`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

