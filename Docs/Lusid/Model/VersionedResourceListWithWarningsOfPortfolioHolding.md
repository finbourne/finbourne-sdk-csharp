# Finbourne.Sdk.Lusid.Model.VersionedResourceListWithWarningsOfPortfolioHolding

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Values** | [List&lt;PortfolioHolding&gt;](PortfolioHolding.md) | Required | The resources to list. |
| **Href** | **string** | Optional | The URI of the resource list. |
| **NextPage** | **string** | Optional | The next page of results. |
| **PreviousPage** | **string** | Optional | The previous page of results. |
| **Warnings** | [List&lt;Warning&gt;](Warning.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VersionedResourceListWithWarningsOfPortfolioHolding(
    varVersion: new ModelVersion(...),  // required
    values: new List<PortfolioHolding>(),  // required — The resources to list.
    href: "...",  // optional — The URI of the resource list.
    nextPage: "...",  // optional — The next page of results.
    previousPage: "...",  // optional — The previous page of results.
    warnings: new List<Warning>(),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VersionedResourceListWithWarningsOfPortfolioHolding>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [PortfolioHolding](PortfolioHolding.md) — used in `Values`
- [Warning](Warning.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

