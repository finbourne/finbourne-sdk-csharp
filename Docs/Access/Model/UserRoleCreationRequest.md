# Finbourne.Sdk.Access.Model.UserRoleCreationRequest

Dto used to request creating a user's role
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UserId** | **string** | Required | The Id of the user for whom to create the role. |
| **Resource** | [PolicyIdRoleResource](PolicyIdRoleResource.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new UserRoleCreationRequest(
    userId: "...",  // required — The Id of the user for whom to create the role.
    resource: new PolicyIdRoleResource(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UserRoleCreationRequest>(json);
```

- [PolicyIdRoleResource](PolicyIdRoleResource.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

