# Finbourne.Sdk.Lusid.Model.CorporateActionSource

A corporate action source
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the corporate action source |
| **Description** | **string** | Optional | The description of the corporate action source |
| **InstrumentScopes** | **List&lt;string&gt;** | Optional | The list of instrument scopes used as the scope resolution strategy when resolving instruments of upserted corporate actions. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CorporateActionSource(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    displayName: "...",  // optional — The name of the corporate action source
    description: "...",  // optional — The description of the corporate action source
    instrumentScopes: ,  // optional — The list of instrument scopes used as the scope resolution strategy when resolving instruments of upserted corporate actions.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CorporateActionSource>(json);
```

- [ResourceId](ResourceId.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

