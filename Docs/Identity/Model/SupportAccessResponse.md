# Finbourne.Sdk.Identity.Model.SupportAccessResponse

Timestamped successful response to grant access to your account
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | ID of the support access request |
| **Duration** | **string** | Required | The duration for which access is requested (in any ISO-8601 format) |
| **Description** | **string** | Optional | The description of why the support access has been granted (i.e. support ticket numbers) |
| **CreatedAt** | **DateTimeOffset** | Required | DateTimeOffset at which the access was granted |
| **Expiry** | **DateTimeOffset** | Required | DateTimeOffset at which the access will be revoked |
| **CreatedBy** | **string** | Required | Obfuscated UserId of the user who granted the support access |
| **Terminated** | **bool** | Optional | Whether or not that access has been invalidated |
| **TerminatedAt** | **DateTimeOffset?** | Optional | DateTimeOffset at which the access was invalidated |
| **TerminatedBy** | **string** | Optional | Obfuscated UserId of the user who revoked the access |
| **PermittedRoles** | **List&lt;string&gt;** | Optional | A list of permitted roles, valid for support staff to assume, for the duration of the access request |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SupportAccessResponse(
    id: "...",  // required — ID of the support access request
    duration: "...",  // required — The duration for which access is requested (in any ISO-8601 format)
    description: "...",  // optional — The description of why the support access has been granted (i.e. support ticket numbers)
    createdAt: DateTimeOffset.Now,  // required — DateTimeOffset at which the access was granted
    expiry: DateTimeOffset.Now,  // required — DateTimeOffset at which the access will be revoked
    createdBy: "...",  // required — Obfuscated UserId of the user who granted the support access
    terminated: true,  // optional — Whether or not that access has been invalidated
    terminatedAt: DateTimeOffset.Now,  // optional — DateTimeOffset at which the access was invalidated
    terminatedBy: "...",  // optional — Obfuscated UserId of the user who revoked the access
    permittedRoles:   // optional — A list of permitted roles, valid for support staff to assume, for the duration of the access request
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupportAccessResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

