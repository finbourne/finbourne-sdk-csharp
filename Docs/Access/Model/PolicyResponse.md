# Finbourne.Sdk.Access.Model.PolicyResponse

Response object from the policy API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [PolicyId](PolicyId.md) | Optional | *No description available.* |
| **Description** | **string** | Optional | Description of what the policy is entitling |
| **Applications** | **List&lt;string&gt;** | Optional | Applications to which the policy applies |
| **Grant** | **Grant** | Optional | *No description available.* |
| **Selectors** | [List&lt;SelectorDefinition&gt;](SelectorDefinition.md) | Optional | Selectors that this policy will be applied to |
| **For** | [List&lt;ForSpec&gt;](ForSpec.md) | Optional | \&quot;For Specification\&quot; for when the policy is to be applied |
| **If** | [List&lt;IfExpression&gt;](IfExpression.md) | Optional | \&quot;If Specification\&quot; for when the policy is to be applied |
| **When** | [WhenSpec](WhenSpec.md) | Optional | *No description available.* |
| **How** | [HowSpec](HowSpec.md) | Optional | *No description available.* |
| **TemplateMetadata** | [TemplateMetadata](TemplateMetadata.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicyResponse(
    id: new PolicyId(...),  // optional
    description: "...",  // optional — Description of what the policy is entitling
    applications: ,  // optional — Applications to which the policy applies
    grant: ,  // optional
    selectors: new List<SelectorDefinition>(),  // optional — Selectors that this policy will be applied to
    varFor: new List<ForSpec>(),  // optional — \&quot;For Specification\&quot; for when the policy is to be applied
    varIf: new List<IfExpression>(),  // optional — \&quot;If Specification\&quot; for when the policy is to be applied
    when: new WhenSpec(...),  // optional
    how: new HowSpec(...),  // optional
    templateMetadata: new TemplateMetadata(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicyResponse>(json);
```


## Related Models

- [PolicyId](PolicyId.md)
- [SelectorDefinition](SelectorDefinition.md) — used in `Selectors`
- [ForSpec](ForSpec.md) — used in `For`
- [IfExpression](IfExpression.md) — used in `If`
- [WhenSpec](WhenSpec.md)
- [HowSpec](HowSpec.md)
- [TemplateMetadata](TemplateMetadata.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

