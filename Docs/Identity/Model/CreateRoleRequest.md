# Finbourne.Sdk.Identity.Model.CreateRoleRequest

Specifies the information required to create a new role.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The role name, which must be unique within the system. |
| **Description** | **string** | Optional | The description for this role |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new CreateRoleRequest(
    name: "...",  // required — The role name, which must be unique within the system.
    description: "..."  // optional — The description for this role
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateRoleRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

