# Finbourne.Sdk.Lusid.Model.WorkspaceItem

An item stored in a workspace.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of the workspace item. |
| **Format** | **int** | Required | A simple integer format identifier. |
| **Name** | **string** | Required | A workspace item&#39;s name. |
| **Group** | **string** | Required | The group containing a workspace item. |
| **Description** | **string** | Required | The description of a workspace item. |
| **Content** | **Object** | Required | The content associated with a workspace item. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WorkspaceItem(
    type: "...",  // required — The type of the workspace item.
    format: 0,  // required — A simple integer format identifier.
    name: "...",  // required — A workspace item&#39;s name.
    group: "...",  // required — The group containing a workspace item.
    description: "...",  // required — The description of a workspace item.
    content: ,  // required — The content associated with a workspace item.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkspaceItem>(json);
```

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

