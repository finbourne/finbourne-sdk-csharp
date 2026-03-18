# Finbourne.Sdk.Access.Model.AttachedPolicyDefinitionResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourceRole** | [RoleId](RoleId.md) | Optional | *No description available.* |
| **RoleHierarchyIndex** | **int** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Applications** | **List&lt;string&gt;** | Optional | *No description available.* |
| **PolicyType** | **PolicyType** | Optional | *No description available.* |
| **Id** | [PolicyId](PolicyId.md) | Optional | *No description available.* |
| **Grant** | **Grant** | Optional | *No description available.* |
| **Selectors** | [List&lt;SelectorDefinition&gt;](SelectorDefinition.md) | Optional | *No description available.* |
| **For** | [List&lt;ForSpec&gt;](ForSpec.md) | Optional | *No description available.* |
| **If** | [List&lt;IfExpression&gt;](IfExpression.md) | Optional | *No description available.* |
| **When** | [WhenSpec](WhenSpec.md) | Optional | *No description available.* |
| **How** | [HowSpec](HowSpec.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new AttachedPolicyDefinitionResponse(
    sourceRole: new RoleId(...),  // optional
    roleHierarchyIndex: 0,  // optional
    description: "...",  // optional
    applications: ,  // optional
    policyType: ,  // optional
    id: new PolicyId(...),  // optional
    grant: ,  // optional
    selectors: new List<SelectorDefinition>(),  // optional
    varFor: new List<ForSpec>(),  // optional
    varIf: new List<IfExpression>(),  // optional
    when: new WhenSpec(...),  // optional
    how: new HowSpec(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AttachedPolicyDefinitionResponse>(json);
```


## Related Models

- [RoleId](RoleId.md)
- [PolicyId](PolicyId.md)
- [SelectorDefinition](SelectorDefinition.md)
- [ForSpec](ForSpec.md)
- [IfExpression](IfExpression.md)
- [WhenSpec](WhenSpec.md)
- [HowSpec](HowSpec.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

