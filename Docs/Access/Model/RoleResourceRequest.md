# Finbourne.Sdk.Access.Model.RoleResourceRequest

RoleResourceRequest
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NonTransitiveSupervisorRoleResource** | [NonTransitiveSupervisorRoleResource](NonTransitiveSupervisorRoleResource.md) | Optional | *No description available.* |
| **PolicyIdRoleResource** | [PolicyIdRoleResource](PolicyIdRoleResource.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new RoleResourceRequest(
    nonTransitiveSupervisorRoleResource: new NonTransitiveSupervisorRoleResource(...),  // optional
    policyIdRoleResource: new PolicyIdRoleResource(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RoleResourceRequest>(json);
```


## Related Models

- [NonTransitiveSupervisorRoleResource](NonTransitiveSupervisorRoleResource.md)
- [PolicyIdRoleResource](PolicyIdRoleResource.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

