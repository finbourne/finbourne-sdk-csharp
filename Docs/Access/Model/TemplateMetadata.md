# Finbourne.Sdk.Access.Model.TemplateMetadata

Extra policy template metadata information, used during a generation request
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TemplateSelection** | [List&lt;TemplateSelection&gt;](TemplateSelection.md) | Optional | List of policy templates used for a generation request |
| **BuildAsAt** | **DateTimeOffset** | Optional | Policy template build AsAt time used for a generation request |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new TemplateMetadata(
    templateSelection: new List<TemplateSelection>(),  // optional — List of policy templates used for a generation request
    buildAsAt: DateTimeOffset.Now  // optional — Policy template build AsAt time used for a generation request
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TemplateMetadata>(json);
```


## Related Models

- [TemplateSelection](TemplateSelection.md) — used in `TemplateSelection`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

