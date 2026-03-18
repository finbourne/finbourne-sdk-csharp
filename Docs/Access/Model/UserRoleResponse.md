# Finbourne.Sdk.Access.Model.UserRoleResponse

Response object from the user role API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Resource** | [RoleResourceRequest](RoleResourceRequest.md) | Required | *No description available.* |
| **Id** | [RoleId](RoleId.md) | Required | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new UserRoleResponse(
    resource: new RoleResourceRequest(...),  // required
    id: new RoleId(...),  // required
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UserRoleResponse>(json);
```


## Related Models

- [RoleResourceRequest](RoleResourceRequest.md)
- [RoleId](RoleId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

