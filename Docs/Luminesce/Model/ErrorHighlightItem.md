# Finbourne.Sdk.Luminesce.Model.ErrorHighlightItem

Representation of a sql error
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Start** | [CursorPosition](CursorPosition.md) | Required | *No description available.* |
| **Stop** | [CursorPosition](CursorPosition.md) | Required | *No description available.* |
| **NoViableAlternativeStart** | [CursorPosition](CursorPosition.md) | Optional | *No description available.* |
| **Length** | **int** | Required | The length of the error token counting line breaks if any |
| **Message** | **string** | Required | The error message |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ErrorHighlightItem(
    start: new CursorPosition(...),  // required
    stop: new CursorPosition(...),  // required
    noViableAlternativeStart: new CursorPosition(...),  // optional
    length: 0,  // required — The length of the error token counting line breaks if any
    message: "..."  // required — The error message
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ErrorHighlightItem>(json);
```


## Related Models

- [CursorPosition](CursorPosition.md)
- [CursorPosition](CursorPosition.md)
- [CursorPosition](CursorPosition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

