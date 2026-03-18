# Finbourne.Sdk.Lusid.Model.Change

The time an entity was modified (amendment and/or historical correction).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | *No description available.* |
| **EntityId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Corrected** | **bool** | Required | *No description available.* |
| **CorrectionEffectiveAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **CorrectionAsAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **Amended** | **bool** | Required | *No description available.* |
| **AmendmentEffectiveAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **AmendmentAsAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Change(
    href: "...",  // optional
    entityId: new ResourceId(...),  // required
    corrected: true,  // required
    correctionEffectiveAt: DateTimeOffset.Now,  // optional
    correctionAsAt: DateTimeOffset.Now,  // optional
    amended: true,  // required
    amendmentEffectiveAt: DateTimeOffset.Now,  // optional
    amendmentAsAt: DateTimeOffset.Now,  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Change>(json);
```

- [ResourceId](ResourceId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

