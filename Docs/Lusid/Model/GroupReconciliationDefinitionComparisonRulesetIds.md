# Finbourne.Sdk.Lusid.Model.GroupReconciliationDefinitionComparisonRulesetIds

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionReconciliation** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **HoldingReconciliation** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ValuationReconciliation** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationDefinitionComparisonRulesetIds(
    transactionReconciliation: new ResourceId(...),  // optional
    holdingReconciliation: new ResourceId(...),  // optional
    valuationReconciliation: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationDefinitionComparisonRulesetIds>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

