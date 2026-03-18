# Finbourne.Sdk.Lusid.Model.ExpandedGroup

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the portfolio group. |
| **Description** | **string** | Optional | The long form description of the portfolio group. |
| **Values** | [List&lt;CompletePortfolio&gt;](CompletePortfolio.md) | Optional | The collection of resource identifiers for the portfolios contained in the portfolio group. |
| **SubGroups** | [List&lt;ExpandedGroup&gt;](ExpandedGroup.md) | Optional | The collection of resource identifiers for the portfolio groups contained in the portfolio group as sub groups. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExpandedGroup(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the portfolio group.
    description: "...",  // optional — The long form description of the portfolio group.
    values: new List<CompletePortfolio>(),  // optional — The collection of resource identifiers for the portfolios contained in the portfolio group.
    subGroups: new List<ExpandedGroup>(),  // optional — The collection of resource identifiers for the portfolio groups contained in the portfolio group as sub groups.
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
var instance = JsonConvert.DeserializeObject<ExpandedGroup>(json);
```

- [ResourceId](ResourceId.md)
- [CompletePortfolio](CompletePortfolio.md) — used in `Values`
- [ExpandedGroup](ExpandedGroup.md) — used in `SubGroups`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

