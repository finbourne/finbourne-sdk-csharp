# Finbourne.Sdk.Lusid.Model.ChangeHistory

A group of changes made by the same person at the same time.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UserId** | **string** | Required | The unique identifier of the user that made the change. |
| **ModifiedAsAt** | **DateTimeOffset** | Required | The date/time of the change. |
| **RequestId** | **string** | Required | The unique identifier of the request that the changes were part of. |
| **Action** | **string** | Required | The action performed on the transaction, either created, updated, or deleted. The available values are: Create, Update, Delete |
| **Changes** | [List&lt;ChangeItem&gt;](ChangeItem.md) | Required | The collection of changes that were made. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ChangeHistory(
    userId: "...",  // required — The unique identifier of the user that made the change.
    modifiedAsAt: DateTimeOffset.Now,  // required — The date/time of the change.
    requestId: "...",  // required — The unique identifier of the request that the changes were part of.
    action: "...",  // required — The action performed on the transaction, either created, updated, or deleted. The available values are: Create, Update, Delete
    changes: new List<ChangeItem>(),  // required — The collection of changes that were made.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ChangeHistory>(json);
```

- [ChangeItem](ChangeItem.md) — used in `Changes`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

