# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3FilterNode

A node in a rule's filter tree: either a group combining child nodes with all/any, or a leaf condition.  The concrete kind is named by the FilterNodeType property.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FilterNodeType** | **string** | Required | Available values: ComplianceRuleV3FilterGroup, ComplianceRuleV3FilterCondition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3FilterNode(
    filterNodeType: "..."  // required — Available values: ComplianceRuleV3FilterGroup, ComplianceRuleV3FilterCondition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3FilterNode>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

