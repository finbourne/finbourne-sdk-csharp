# Finbourne.Sdk.Lusid.Model.HoldingContributor

A list of transactions contributed to a holding.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Transaction** | [Transaction](Transaction.md) | Required | *No description available.* |
| **HoldingId** | **long?** | Optional | The unique holding identifier |
| **Movements** | [List&lt;MovementSettlementSummary&gt;](MovementSettlementSummary.md) | Optional | Movements contributed to holding |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HoldingContributor(
    transaction: new Transaction(...),  // required
    holdingId: 0L,  // optional — The unique holding identifier
    movements: new List<MovementSettlementSummary>()  // optional — Movements contributed to holding
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HoldingContributor>(json);
```


## Related Models

- [Transaction](Transaction.md)
- [MovementSettlementSummary](MovementSettlementSummary.md) — used in `Movements`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

