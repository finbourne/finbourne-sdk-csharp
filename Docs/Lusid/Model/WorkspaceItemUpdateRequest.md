# Finbourne.Sdk.Lusid.Model.WorkspaceItemUpdateRequest

A request to update a workspace item.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Format** | **int** | Required | A simple integer format identifier. |
| **Description** | **string** | Required | The description of a workspace item. |
| **Content** | **Object** | Required | The content associated with a workspace item. |
| **Type** | **string** | Required | The type of the workspace item. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WorkspaceItemUpdateRequest(
    format: 0,  // required — A simple integer format identifier.
    description: "...",  // required — The description of a workspace item.
    content: ,  // required — The content associated with a workspace item.
    type: "..."  // required — The type of the workspace item.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkspaceItemUpdateRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

