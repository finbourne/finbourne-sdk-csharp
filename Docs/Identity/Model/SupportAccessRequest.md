# Finbourne.Sdk.Identity.Model.SupportAccessRequest

A Request to grant support access to your account
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Duration** | **string** | Required | The duration for which access is requested (in any ISO-8601 format) |
| **Description** | **string** | Optional | The description of why the support access has been granted (i.e. support ticket numbers) |
| **PermittedRoles** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SupportAccessRequest(
    duration: "...",  // required — The duration for which access is requested (in any ISO-8601 format)
    description: "...",  // optional — The description of why the support access has been granted (i.e. support ticket numbers)
    permittedRoles:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupportAccessRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

