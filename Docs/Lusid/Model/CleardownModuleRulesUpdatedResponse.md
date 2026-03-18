# Finbourne.Sdk.Lusid.Model.CleardownModuleRulesUpdatedResponse

A Cleardown Module rules update response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Rules** | [List&lt;CleardownModuleRule&gt;](CleardownModuleRule.md) | Optional | The Cleardown Rules that apply for the Cleardown Module. Rules are evaluated in the order they occur in this collection. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CleardownModuleRulesUpdatedResponse(
    rules: new List<CleardownModuleRule>(),  // optional — The Cleardown Rules that apply for the Cleardown Module. Rules are evaluated in the order they occur in this collection.
    varVersion: new ModelVersion(...),  // optional
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CleardownModuleRulesUpdatedResponse>(json);
```


## Related Models

- [CleardownModuleRule](CleardownModuleRule.md) — used in `Rules`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

