# Finbourne.Sdk.Lusid.Model.SettleExpectedActivityWritebackSuggestion

Suggests a settlement instruction that settles the expected activity of the target item, using the  settlement confirmed by the origin item on the other side of the result. The request is upsertable as-is.
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

var instance = new SettleExpectedActivityWritebackSuggestion(
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
var instance = JsonConvert.DeserializeObject<SettleExpectedActivityWritebackSuggestion>(json);
```


## Related Models

- [WritebackResultPattern](WritebackResultPattern.md)
- [ResourceId](ResourceId.md)
- [SettlementInstructionRequest](SettlementInstructionRequest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

