# Finbourne.Sdk.Lusid.Model.ItemAndWorkspace

An item plus its containing workspace name.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WorkspaceName** | **string** | Required | A workspace&#39;s name. |
| **WorkspaceItem** | [WorkspaceItem](WorkspaceItem.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ItemAndWorkspace(
    workspaceName: "...",  // required — A workspace&#39;s name.
    workspaceItem: new WorkspaceItem(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ItemAndWorkspace>(json);
```

- [WorkspaceItem](WorkspaceItem.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

