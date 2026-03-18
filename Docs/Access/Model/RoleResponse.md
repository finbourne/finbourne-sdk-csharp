# Finbourne.Sdk.Access.Model.RoleResponse

Response object from the role API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [RoleId](RoleId.md) | Required | *No description available.* |
| **RoleHierarchyIndex** | **int** | Required | The hierarchical index of the role |
| **Description** | **string** | Optional | The description of the role |
| **Resource** | [RoleResourceRequest](RoleResourceRequest.md) | Required | *No description available.* |
| **When** | [WhenSpec](WhenSpec.md) | Required | *No description available.* |
| **Permission** | **string** | Required | The action key of the role |
| **Limit** | **Dictionary&lt;string, string&gt;** | Optional | The identifiers of the role with the maximum privileges that this role can have |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new RoleResponse(
    id: new RoleId(...),  // required
    roleHierarchyIndex: 0,  // required — The hierarchical index of the role
    description: "...",  // optional — The description of the role
    resource: new RoleResourceRequest(...),  // required
    when: new WhenSpec(...),  // required
    permission: "...",  // required — The action key of the role
    limit: ,  // optional — The identifiers of the role with the maximum privileges that this role can have
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RoleResponse>(json);
```


## Related Models

- [RoleId](RoleId.md)
- [RoleResourceRequest](RoleResourceRequest.md)
- [WhenSpec](WhenSpec.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

