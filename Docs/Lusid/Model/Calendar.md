# Finbourne.Sdk.Lusid.Model.Calendar

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | *No description available.* |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Type** | **string** | Required | *No description available.* |
| **WeekendMask** | [WeekendMask](WeekendMask.md) | Required | *No description available.* |
| **SourceProvider** | **string** | Required | *No description available.* |
| **Properties** | [List&lt;Property&gt;](Property.md) | Required | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Calendar(
    href: "...",  // optional
    id: new ResourceId(...),  // required
    type: "...",  // required
    weekendMask: new WeekendMask(...),  // required
    sourceProvider: "...",  // required
    properties: new List<Property>(),  // required
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
var instance = JsonConvert.DeserializeObject<Calendar>(json);
```

- [ResourceId](ResourceId.md)
- [WeekendMask](WeekendMask.md)
- [Property](Property.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

