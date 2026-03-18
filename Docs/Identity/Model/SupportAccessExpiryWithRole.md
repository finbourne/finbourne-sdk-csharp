# Finbourne.Sdk.Identity.Model.SupportAccessExpiryWithRole

Time at which the support access granted for a role expires
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Expiry** | **DateTimeOffset** | Required | DateTimeOffset at which the access will be revoked |
| **PermittedRole** | **string** | Required | Unique identifier for permitted role.  Use GET /identity/api/authentication/support-roles to lookup role label/code from identifier. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SupportAccessExpiryWithRole(
    expiry: DateTimeOffset.Now,  // required — DateTimeOffset at which the access will be revoked
    permittedRole: "..."  // required — Unique identifier for permitted role.  Use GET /identity/api/authentication/support-roles to lookup role label/code from identifier.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupportAccessExpiryWithRole>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

