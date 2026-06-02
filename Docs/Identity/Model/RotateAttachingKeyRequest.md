# Finbourne.Sdk.Identity.Model.RotateAttachingKeyRequest

Request body for rotating the Attaching Key on a cell that is already Attached to a parent admin domain. Carries only the new PAT value — the parent identity is already pinned on the cell from the original `SetAttachingKey` handshake and the source of truth for all later operations.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Pat** | **string** | Required | New Attaching Key PAT to persist. Same length / content constraints as the original Finbourne.Lydia.WebApi.Dtos.CellManagement.SetAttachingKeyRequest.Pat: a &#x60;StringSecurityCheck&#x60; catch-all plus a strict opaque-token character set so the request body cannot smuggle in HTML / SQL / script content. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new RotateAttachingKeyRequest(
    pat: "..."  // required — New Attaching Key PAT to persist. Same length / content constraints as the original Finbourne.Lydia.WebApi.Dtos.CellManagement.SetAttachingKeyRequest.Pat: a &#x60;StringSecurityCheck&#x60; catch-all plus a strict opaque-token character set so the request body cannot smuggle in HTML / SQL / script content.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RotateAttachingKeyRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

