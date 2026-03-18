# Finbourne.Sdk.Lusid.Model.ReconciledTransaction

Information about reconciled transactions.  At least one of Left and Right will be populated.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **Right** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **PercentageMatch** | **decimal** | Optional | How good a match this is considered to be. |
| **MappingRuleSetResults** | **List&lt;bool&gt;** | Optional | The result of each individual mapping rule result.  Will only be present if both Left and Right are populated. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciledTransaction(
    left: new Transaction(...),  // optional
    right: new Transaction(...),  // optional
    percentageMatch: 0.0d,  // optional — How good a match this is considered to be.
    mappingRuleSetResults:   // optional — The result of each individual mapping rule result.  Will only be present if both Left and Right are populated.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciledTransaction>(json);
```


## Related Models

- [Transaction](Transaction.md)
- [Transaction](Transaction.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

