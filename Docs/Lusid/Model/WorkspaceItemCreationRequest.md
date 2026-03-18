# Finbourne.Sdk.Lusid.Model.WorkspaceItemCreationRequest

A request to create an item in a workspace.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Format** | **int** | Required | A simple integer format identifier. |
| **Name** | **string** | Required | A workspace item&#39;s name. |
| **Group** | **string** | Required | The group containing a workspace item. |
| **Description** | **string** | Required | The description of a workspace item. |
| **Content** | **Object** | Required | The content associated with a workspace item. |
| **Type** | **string** | Required | The type of the workspace item. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WorkspaceItemCreationRequest(
    format: 0,  // required — A simple integer format identifier.
    name: "...",  // required — A workspace item&#39;s name.
    group: "...",  // required — The group containing a workspace item.
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
var instance = JsonConvert.DeserializeObject<WorkspaceItemCreationRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

