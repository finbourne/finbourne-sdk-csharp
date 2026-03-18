# Finbourne.Sdk.Lusid.Model.Schema

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Entity** | **string** | Optional | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Values** | [Dictionary&lt;string, FieldSchema&gt;](FieldSchema.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Schema(
    entity: "...",  // optional
    href: "...",  // optional
    values: new FieldSchema(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Schema>(json);
```

- [FieldSchema](FieldSchema.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

