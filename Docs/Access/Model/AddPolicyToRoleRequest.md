# Finbourne.Sdk.Access.Model.AddPolicyToRoleRequest

Request body used to add Policies to a Role
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Policies** | [List&lt;PolicyId&gt;](PolicyId.md) | Required | Identifiers of policies to add to a role |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new AddPolicyToRoleRequest(
    policies: new List<PolicyId>()  // required — Identifiers of policies to add to a role
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddPolicyToRoleRequest>(json);
```


## Related Models

- [PolicyId](PolicyId.md) — used in `Policies`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

