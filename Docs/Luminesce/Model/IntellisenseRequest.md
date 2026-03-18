# Finbourne.Sdk.Luminesce.Model.IntellisenseRequest

Representation of a request for IntellisenseItems
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Lines** | **List&lt;string&gt;** | Required | The lines of text the user currently has in the editor |
| **Position** | [CursorPosition](CursorPosition.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new IntellisenseRequest(
    lines: ,  // required — The lines of text the user currently has in the editor
    position: new CursorPosition(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntellisenseRequest>(json);
```

- [CursorPosition](CursorPosition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

