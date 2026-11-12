# Finbourne.Sdk.Lusid.Model.TaxClassificationDetail

A single instrument's classification with the version history of every input behind it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Classification** | [TaxClassification](TaxClassification.md) | Required | *No description available.* |
| **History** | [List&lt;TaxClassificationFieldVersion&gt;](TaxClassificationFieldVersion.md) | Required | Every version of every classification input and override for the instrument, oldest first. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxClassificationDetail(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    classification: new TaxClassification(...),  // required
    history: new List<TaxClassificationFieldVersion>(),  // required — Every version of every classification input and override for the instrument, oldest first.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxClassificationDetail>(json);
```

- [TaxClassification](TaxClassification.md)
- [TaxClassificationFieldVersion](TaxClassificationFieldVersion.md) — used in `History`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

