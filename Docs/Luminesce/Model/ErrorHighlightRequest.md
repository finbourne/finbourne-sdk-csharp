# Finbourne.Sdk.Luminesce.Model.ErrorHighlightRequest

Request for Error highlighting
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Lines** | **List&lt;string&gt;** | Required | The lines of text the user currently has in the editor |
| **EnsureSomeTextIsSelected** | **bool** | Optional | If an editor requires some selection of non-whitespace this can be set to true to force at least one visible character to be selected. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ErrorHighlightRequest(
    lines: ,  // required — The lines of text the user currently has in the editor
    ensureSomeTextIsSelected: true  // optional — If an editor requires some selection of non-whitespace this can be set to true to force at least one visible character to be selected.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ErrorHighlightRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

