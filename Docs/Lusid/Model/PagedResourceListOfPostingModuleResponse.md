# Finbourne.Sdk.Lusid.Model.PagedResourceListOfPostingModuleResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |
| **Values** | [List&lt;PostingModuleResponse&gt;](PostingModuleResponse.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PagedResourceListOfPostingModuleResponse(
    nextPage: "...",  // optional
    previousPage: "...",  // optional
    values: new List<PostingModuleResponse>(),  // required
    href: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PagedResourceListOfPostingModuleResponse>(json);
```

- [PostingModuleResponse](PostingModuleResponse.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

