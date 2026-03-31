# Finbourne.Sdk.Lusid.Model.WorkspacePermittedItemActions

The workspace item actions a user is permitted to perform within a workspace.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReadItem** | **bool** | Optional | Whether the user is permitted to read workspace items. |
| **AddItem** | **bool** | Optional | Whether the user is permitted to add workspace items. |
| **UpdateItem** | **bool** | Optional | Whether the user is permitted to update workspace items. |
| **DeleteItem** | **bool** | Optional | Whether the user is permitted to delete workspace items. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WorkspacePermittedItemActions(
    readItem: true,  // optional — Whether the user is permitted to read workspace items.
    addItem: true,  // optional — Whether the user is permitted to add workspace items.
    updateItem: true,  // optional — Whether the user is permitted to update workspace items.
    deleteItem: true  // optional — Whether the user is permitted to delete workspace items.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkspacePermittedItemActions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

