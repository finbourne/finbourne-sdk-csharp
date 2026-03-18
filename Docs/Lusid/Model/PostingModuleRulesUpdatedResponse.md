# Finbourne.Sdk.Lusid.Model.PostingModuleRulesUpdatedResponse

A Posting Module rules update response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Rules** | [List&lt;PostingModuleRule&gt;](PostingModuleRule.md) | Optional | The Posting Rules that apply for the Posting Module. Rules are evaluated in the order they occur in this collection. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PostingModuleRulesUpdatedResponse(
    rules: new List<PostingModuleRule>(),  // optional — The Posting Rules that apply for the Posting Module. Rules are evaluated in the order they occur in this collection.
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
var instance = JsonConvert.DeserializeObject<PostingModuleRulesUpdatedResponse>(json);
```


## Related Models

- [PostingModuleRule](PostingModuleRule.md) — used in `Rules`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

