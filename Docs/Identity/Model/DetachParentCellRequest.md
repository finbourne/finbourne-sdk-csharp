# Finbourne.Sdk.Identity.Model.DetachParentCellRequest

Request body for `DetachParentCell`. The endpoint uses a double-invoke pattern: the first call (Finbourne.Lydia.WebApi.Dtos.CellManagement.DetachParentCellRequest.Confirm=false) transitions the cell into Finbourne.Lydia.Postgres.Database.DTO.AttachmentStatus.Detaching; the second call (Finbourne.Lydia.WebApi.Dtos.CellManagement.DetachParentCellRequest.Confirm=true) performs the actual detach.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Confirm** | **bool** | Optional | False to mark the cell as &#x60;Detaching&#x60;; true to execute the detach. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new DetachParentCellRequest(
    confirm: true  // optional — False to mark the cell as &#x60;Detaching&#x60;; true to execute the detach.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DetachParentCellRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

