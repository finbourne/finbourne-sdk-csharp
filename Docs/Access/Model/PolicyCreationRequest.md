# Finbourne.Sdk.Access.Model.PolicyCreationRequest

Request to create a policy
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | Code of the policy being created |
| **Description** | **string** | Optional | Description of what the policy will be used for |
| **Applications** | **List&lt;string&gt;** | Optional | Applications this policy is used with |
| **Grant** | **Grant** | Required | *No description available.* |
| **Selectors** | [List&lt;SelectorDefinition&gt;](SelectorDefinition.md) | Required | Selectors that identify what resources this policy qualifies for |
| **For** | [List&lt;ForSpec&gt;](ForSpec.md) | Optional | \&quot;For Specification\&quot; for when the policy is to be applied |
| **If** | [List&lt;IfExpression&gt;](IfExpression.md) | Optional | \&quot;If Specification\&quot; for when the policy is to be applied |
| **When** | [WhenSpec](WhenSpec.md) | Required | *No description available.* |
| **How** | [HowSpec](HowSpec.md) | Optional | *No description available.* |
| **TemplateMetadata** | [TemplateMetadata](TemplateMetadata.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicyCreationRequest(
    code: "...",  // required — Code of the policy being created
    description: "...",  // optional — Description of what the policy will be used for
    applications: ,  // optional — Applications this policy is used with
    grant: ,  // required
    selectors: new List<SelectorDefinition>(),  // required — Selectors that identify what resources this policy qualifies for
    varFor: new List<ForSpec>(),  // optional — \&quot;For Specification\&quot; for when the policy is to be applied
    varIf: new List<IfExpression>(),  // optional — \&quot;If Specification\&quot; for when the policy is to be applied
    when: new WhenSpec(...),  // required
    how: new HowSpec(...),  // optional
    templateMetadata: new TemplateMetadata(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicyCreationRequest>(json);
```

- [SelectorDefinition](SelectorDefinition.md) — used in `Selectors`
- [ForSpec](ForSpec.md) — used in `For`
- [IfExpression](IfExpression.md) — used in `If`
- [WhenSpec](WhenSpec.md)
- [HowSpec](HowSpec.md)
- [TemplateMetadata](TemplateMetadata.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

