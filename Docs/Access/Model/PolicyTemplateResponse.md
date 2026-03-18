# Finbourne.Sdk.Access.Model.PolicyTemplateResponse

Response object for a policy template
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Optional | Display name of the policy template being created |
| **Scope** | **string** | Optional | The Scope of the policy template being created |
| **Code** | **string** | Optional | The Code of the policy template being created |
| **Description** | **string** | Optional | Description of the policy template being created |
| **Applications** | **List&lt;string&gt;** | Optional | List of applications that this policy template covers |
| **Tags** | **List&lt;string&gt;** | Optional | List of policy types that this policy template covers |
| **TemplatedSelectors** | [List&lt;PolicyTemplatedSelector&gt;](PolicyTemplatedSelector.md) | Optional | The selector definitions of policies included in this policy template |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicyTemplateResponse(
    displayName: "...",  // optional — Display name of the policy template being created
    scope: "...",  // optional — The Scope of the policy template being created
    code: "...",  // optional — The Code of the policy template being created
    description: "...",  // optional — Description of the policy template being created
    applications: ,  // optional — List of applications that this policy template covers
    tags: ,  // optional — List of policy types that this policy template covers
    templatedSelectors: new List<PolicyTemplatedSelector>()  // optional — The selector definitions of policies included in this policy template
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicyTemplateResponse>(json);
```

- [PolicyTemplatedSelector](PolicyTemplatedSelector.md) — used in `TemplatedSelectors`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

