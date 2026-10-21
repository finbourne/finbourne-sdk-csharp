# Finbourne.Sdk.Lusid.Model.WithholdingTaxResolutionProvenance

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MatchScore** | **decimal?** | Optional | The share of the main dataset&#39;s dimensions that the row matches, from 0 to 1. Null on an anomaly match. |
| **MatchedFieldCount** | **int?** | Optional | The number of the main dataset&#39;s dimensions that the row matches. Null on an anomaly match. |
| **SourceFilterApplied** | **string** | Optional | The rule source level that matched. Null when no source priority applies. |
| **TieBroken** | **bool** | Required | True when another row matched as well as the winner, so the tie-break order chose: the latest effective date, then the rule id. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxResolutionProvenance(
    matchScore: 0.0d,  // optional — The share of the main dataset&#39;s dimensions that the row matches, from 0 to 1. Null on an anomaly match.
    matchedFieldCount: 0,  // optional — The number of the main dataset&#39;s dimensions that the row matches. Null on an anomaly match.
    sourceFilterApplied: "...",  // optional — The rule source level that matched. Null when no source priority applies.
    tieBroken: true  // required — True when another row matched as well as the winner, so the tie-break order chose: the latest effective date, then the rule id.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxResolutionProvenance>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

