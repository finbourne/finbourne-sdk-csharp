# Finbourne.Sdk.Workflow.Model.DeletedEntityResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The Uri related to this Entity |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The EffectiveFrom for this response |
| **AsAt** | **DateTimeOffset** | Required | The AsAt for this response |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new DeletedEntityResponse(
    href: "...",  // optional — The Uri related to this Entity
    effectiveFrom: DateTimeOffset.Now,  // optional — The EffectiveFrom for this response
    asAt: DateTimeOffset.Now,  // required — The AsAt for this response
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeletedEntityResponse>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

