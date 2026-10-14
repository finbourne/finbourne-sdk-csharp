# Finbourne.Sdk.Lusid.Model.WritebackSuggestion

A writeback suggested against a target-side item of a rec result. Polymorphic by WritebackType; each  supported type has a corresponding inherited class carrying the upsertable request it proposes.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ResultPattern** | [WritebackResultPattern](WritebackResultPattern.md) | Required | *No description available.* |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **SettlementInstructionRequest** | [SettlementInstructionRequest](SettlementInstructionRequest.md) | Required | *No description available.* |
| **WritebackType** | **string** | Required | Polymorphic discriminator, carrying the same values as writebackType on the matching ruleset&#39;s writeback configuration. Supported types: SettleExpectedActivity. Available values: SettleExpectedActivity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WritebackSuggestion(
    resultPattern: new WritebackResultPattern(...),  // required
    portfolioId: new ResourceId(...),  // required
    settlementInstructionRequest: new SettlementInstructionRequest(...),  // required
    writebackType: "..."  // required — Polymorphic discriminator, carrying the same values as writebackType on the matching ruleset&#39;s writeback configuration. Supported types: SettleExpectedActivity. Available values: SettleExpectedActivity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WritebackSuggestion>(json);
```


## Related Models

- [WritebackResultPattern](WritebackResultPattern.md)
- [ResourceId](ResourceId.md)
- [SettlementInstructionRequest](SettlementInstructionRequest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

