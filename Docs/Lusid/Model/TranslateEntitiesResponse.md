# Finbourne.Sdk.Lusid.Model.TranslateEntitiesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, TranslationResult&gt;](TranslationResult.md) | Optional | The entities that were successfully translated. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The error details corresponding to entities that failed to be translated. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslateEntitiesResponse(
    values: new TranslationResult(...),  // optional — The entities that were successfully translated.
    failed: new ErrorDetail(...),  // optional — The error details corresponding to entities that failed to be translated.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslateEntitiesResponse>(json);
```


## Related Models

- [TranslationResult](TranslationResult.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

