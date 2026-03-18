# Finbourne.Sdk.Lusid.Model.WorkspaceCreationRequest

A request to create an empty workspace.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | A workspace&#39;s name. |
| **Description** | **string** | Required | A friendly description for the workspace. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WorkspaceCreationRequest(
    name: "...",  // required — A workspace&#39;s name.
    description: "..."  // required — A friendly description for the workspace.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkspaceCreationRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

