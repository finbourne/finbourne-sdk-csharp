# Finbourne.Sdk.Lusid.Model.CutLabelDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **CutLocalTime** | [CutLocalTime](CutLocalTime.md) | Optional | *No description available.* |
| **VarTimeZone** | **string** | Optional | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CutLabelDefinition(
    code: "...",  // optional
    displayName: "...",  // optional
    description: "...",  // optional
    cutLocalTime: new CutLocalTime(...),  // optional
    varTimeZone: "...",  // optional
    href: "...",  // optional
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CutLabelDefinition>(json);
```

- [CutLocalTime](CutLocalTime.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

