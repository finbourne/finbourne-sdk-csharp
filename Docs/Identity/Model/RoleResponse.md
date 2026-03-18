# Finbourne.Sdk.Identity.Model.RoleResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The role&#39;s system supplied unique identifier |
| **RoleId** | [RoleId](RoleId.md) | Required | *No description available.* |
| **Source** | **string** | Required | The source of the role |
| **Name** | **string** | Required | The role name, which must be unique within the system. |
| **Description** | **string** | Optional | The description for this role |
| **SamlName** | **string** | Optional | The name to use on the SAML request if assigning this role via SAML Just in Time (JIT) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new RoleResponse(
    id: "...",  // required — The role&#39;s system supplied unique identifier
    roleId: new RoleId(...),  // required
    source: "...",  // required — The source of the role
    name: "...",  // required — The role name, which must be unique within the system.
    description: "...",  // optional — The description for this role
    samlName: "..."  // optional — The name to use on the SAML request if assigning this role via SAML Just in Time (JIT)
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

- [RoleId](RoleId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

