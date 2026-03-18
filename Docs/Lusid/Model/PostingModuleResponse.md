# Finbourne.Sdk.Lusid.Model.PostingModuleResponse

A Posting Module definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **PostingModuleCode** | **string** | Required | The code of the Posting Module. |
| **ChartOfAccountsId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the Posting Module. |
| **Description** | **string** | Optional | A description for the Posting Module. |
| **Rules** | [List&lt;PostingModuleRule&gt;](PostingModuleRule.md) | Optional | The Posting Rules that apply for the Posting Module. Rules are evaluated in the order they occur in this collection. |
| **Status** | **string** | Required | The Posting Module status. Can be Active, Inactive or Deleted. Defaults to Active. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PostingModuleResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    postingModuleCode: "...",  // required — The code of the Posting Module.
    chartOfAccountsId: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the Posting Module.
    description: "...",  // optional — A description for the Posting Module.
    rules: new List<PostingModuleRule>(),  // optional — The Posting Rules that apply for the Posting Module. Rules are evaluated in the order they occur in this collection.
    status: "...",  // required — The Posting Module status. Can be Active, Inactive or Deleted. Defaults to Active.
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
var instance = JsonConvert.DeserializeObject<PostingModuleResponse>(json);
```

- [ResourceId](ResourceId.md)
- [PostingModuleRule](PostingModuleRule.md) — used in `Rules`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

