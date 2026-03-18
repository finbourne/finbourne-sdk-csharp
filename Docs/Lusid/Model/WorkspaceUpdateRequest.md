# Finbourne.Sdk.Lusid.Model.WorkspaceUpdateRequest

A request to update a workspace.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Required | A friendly description for the workspace. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WorkspaceUpdateRequest(
    description: "..."  // required — A friendly description for the workspace.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkspaceUpdateRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

