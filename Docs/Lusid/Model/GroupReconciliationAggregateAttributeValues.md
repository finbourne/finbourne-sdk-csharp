# Finbourne.Sdk.Lusid.Model.GroupReconciliationAggregateAttributeValues

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftAggregateAttributes** | [List&lt;ComparisonAttributeValuePair&gt;](ComparisonAttributeValuePair.md) | Required | Aggregate attribute names and values for the left hand entity being reconciled. |
| **RightAggregateAttributes** | [List&lt;ComparisonAttributeValuePair&gt;](ComparisonAttributeValuePair.md) | Required | Aggregate attribute names and values for the right hand entity being reconciled. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationAggregateAttributeValues(
    leftAggregateAttributes: new List<ComparisonAttributeValuePair>(),  // required — Aggregate attribute names and values for the left hand entity being reconciled.
    rightAggregateAttributes: new List<ComparisonAttributeValuePair>()  // required — Aggregate attribute names and values for the right hand entity being reconciled.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationAggregateAttributeValues>(json);
```


## Related Models

- [ComparisonAttributeValuePair](ComparisonAttributeValuePair.md) — used in `LeftAggregateAttributes`
- [ComparisonAttributeValuePair](ComparisonAttributeValuePair.md) — used in `RightAggregateAttributes`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

