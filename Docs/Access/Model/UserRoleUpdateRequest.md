# Finbourne.Sdk.Access.Model.UserRoleUpdateRequest

Dto used to request updating a user's role
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Resource** | [PolicyIdRoleResource](PolicyIdRoleResource.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new UserRoleUpdateRequest(
    resource: new PolicyIdRoleResource(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UserRoleUpdateRequest>(json);
```


## Related Models

- [PolicyIdRoleResource](PolicyIdRoleResource.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

