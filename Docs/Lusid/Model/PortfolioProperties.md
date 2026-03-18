# Finbourne.Sdk.Lusid.Model.PortfolioProperties

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The portfolio properties. These will be from the &#39;Portfolio&#39; domain. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioProperties(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    properties: new Property(...),  // optional — The portfolio properties. These will be from the &#39;Portfolio&#39; domain.
    varVersion: new ModelVersion(...),  // optional
    stagedModifications: new StagedModificationsInfo(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioProperties>(json);
```

- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

