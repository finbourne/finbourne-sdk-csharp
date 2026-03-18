# Finbourne.Sdk.Lusid.Model.PagedResourceListOfPortfolioSearchResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |
| **Values** | [List&lt;PortfolioSearchResult&gt;](PortfolioSearchResult.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PagedResourceListOfPortfolioSearchResult(
    nextPage: "...",  // optional
    previousPage: "...",  // optional
    values: new List<PortfolioSearchResult>(),  // required
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
var instance = JsonConvert.DeserializeObject<PagedResourceListOfPortfolioSearchResult>(json);
```

- [PortfolioSearchResult](PortfolioSearchResult.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

