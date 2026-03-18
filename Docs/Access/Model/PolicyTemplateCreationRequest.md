# Finbourne.Sdk.Access.Model.PolicyTemplateCreationRequest

Request to create a policy template
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The Code of the policy template being created |
| **DisplayName** | **string** | Required | The display name of the policy template being created |
| **Description** | **string** | Required | Description of the policy template being craeted |
| **TemplatedSelectors** | [List&lt;PolicyTemplatedSelector&gt;](PolicyTemplatedSelector.md) | Required | The selector definitions of policies included in this policy template |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicyTemplateCreationRequest(
    code: "...",  // required — The Code of the policy template being created
    displayName: "...",  // required — The display name of the policy template being created
    description: "...",  // required — Description of the policy template being craeted
    templatedSelectors: new List<PolicyTemplatedSelector>()  // required — The selector definitions of policies included in this policy template
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicyTemplateCreationRequest>(json);
```

- [PolicyTemplatedSelector](PolicyTemplatedSelector.md) — used in `TemplatedSelectors`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

