# Finbourne.Sdk.Access.Model.RoleUpdateRequest

Role update does not allow the changing of the id
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Optional | The description of the role |
| **Resource** | [RoleResourceRequest](RoleResourceRequest.md) | Required | *No description available.* |
| **When** | [WhenSpec](WhenSpec.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new RoleUpdateRequest(
    description: "...",  // optional — The description of the role
    resource: new RoleResourceRequest(...),  // required
    when: new WhenSpec(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RoleUpdateRequest>(json);
```

- [RoleResourceRequest](RoleResourceRequest.md)
- [WhenSpec](WhenSpec.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

