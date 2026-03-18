# Finbourne.Sdk.Lusid.Model.Abor

An Abor entity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Abor. |
| **Description** | **string** | Optional | The description for the Abor. |
| **PortfolioIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | The list with the portfolio ids which are part of the Abor. Note: These must all have the same base currency. |
| **AborConfigurationId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Abor. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **BaseCurrency** | **string** | Optional | The base currency of the abor based on contained portfolio base currencies. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Abor(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    displayName: "...",  // optional — The name of the Abor.
    description: "...",  // optional — The description for the Abor.
    portfolioIds: new List<PortfolioEntityId>(),  // required — The list with the portfolio ids which are part of the Abor. Note: These must all have the same base currency.
    aborConfigurationId: new ResourceId(...),  // optional
    properties: new Property(...),  // optional — A set of properties for the Abor.
    varVersion: new ModelVersion(...),  // optional
    baseCurrency: "...",  // optional — The base currency of the abor based on contained portfolio base currencies.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Abor>(json);
```

- [ResourceId](ResourceId.md)
- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioIds`
- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

