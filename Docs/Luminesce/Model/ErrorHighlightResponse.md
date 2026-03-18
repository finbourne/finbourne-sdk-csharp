# Finbourne.Sdk.Luminesce.Model.ErrorHighlightResponse

Response for error highlighting
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Errors** | [List&lt;ErrorHighlightItem&gt;](ErrorHighlightItem.md) | Required | The errors within the Sql |
| **SqlWithMarker** | **string** | Required | The SQL this is for, with characters indicating the error locations |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ErrorHighlightResponse(
    errors: new List<ErrorHighlightItem>(),  // required — The errors within the Sql
    sqlWithMarker: "..."  // required — The SQL this is for, with characters indicating the error locations
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ErrorHighlightResponse>(json);
```


## Related Models

- [ErrorHighlightItem](ErrorHighlightItem.md) — used in `Errors`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

