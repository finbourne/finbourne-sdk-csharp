# Finbourne.Sdk.Lusid.Model.GroupReconciliationCoreAttributeValues

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftCoreAttributes** | [List&lt;ComparisonAttributeValuePair&gt;](ComparisonAttributeValuePair.md) | Required | Core attribute names and values for the left hand entity being reconciled. |
| **RightCoreAttributes** | [List&lt;ComparisonAttributeValuePair&gt;](ComparisonAttributeValuePair.md) | Required | Core attribute names and values for the right hand entity being reconciled. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationCoreAttributeValues(
    leftCoreAttributes: new List<ComparisonAttributeValuePair>(),  // required — Core attribute names and values for the left hand entity being reconciled.
    rightCoreAttributes: new List<ComparisonAttributeValuePair>()  // required — Core attribute names and values for the right hand entity being reconciled.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationCoreAttributeValues>(json);
```


## Related Models

- [ComparisonAttributeValuePair](ComparisonAttributeValuePair.md) — used in `LeftCoreAttributes`
- [ComparisonAttributeValuePair](ComparisonAttributeValuePair.md) — used in `RightCoreAttributes`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

