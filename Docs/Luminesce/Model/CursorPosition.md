# Finbourne.Sdk.Luminesce.Model.CursorPosition

Represents a cursor location
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Row** | **int** | Required | Row (0 based) of the user&#39;s cursor position |
| **Column** | **int** | Required | Column (0 based) of the user&#39;s cursor position |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CursorPosition(
    row: 0,  // required — Row (0 based) of the user&#39;s cursor position
    column: 0  // required — Column (0 based) of the user&#39;s cursor position
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CursorPosition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

