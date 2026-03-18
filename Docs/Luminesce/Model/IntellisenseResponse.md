# Finbourne.Sdk.Luminesce.Model.IntellisenseResponse

Available intellisense response information
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AutoCompleteList** | [List&lt;IntellisenseItem&gt;](IntellisenseItem.md) | Required | The available items at this point |
| **TryAgainSoonForMore** | **bool** | Required | Should the caller try again soon? (true means a cache is being built and this is a preliminary response!) |
| **SqlWithMarker** | **string** | Required | The SQL this is for with characters indicating the location the pop-up is for |
| **StartReplacementPosition** | [CursorPosition](CursorPosition.md) | Required | *No description available.* |
| **EndReplacementPosition** | [CursorPosition](CursorPosition.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new IntellisenseResponse(
    autoCompleteList: new List<IntellisenseItem>(),  // required — The available items at this point
    tryAgainSoonForMore: true,  // required — Should the caller try again soon? (true means a cache is being built and this is a preliminary response!)
    sqlWithMarker: "...",  // required — The SQL this is for with characters indicating the location the pop-up is for
    startReplacementPosition: new CursorPosition(...),  // required
    endReplacementPosition: new CursorPosition(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntellisenseResponse>(json);
```


## Related Models

- [IntellisenseItem](IntellisenseItem.md) — used in `AutoCompleteList`
- [CursorPosition](CursorPosition.md)
- [CursorPosition](CursorPosition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

