# Finbourne.Sdk.Lusid.Model.CompletePortfolio

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Description** | **string** | Optional | The long form description of the portfolio. |
| **DisplayName** | **string** | Optional | The name of the portfolio. |
| **Created** | **DateTimeOffset** | Optional | The effective datetime at which the portfolio was created. No transactions or constituents can be added to the portfolio before this date. |
| **ParentPortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **IsDerived** | **bool** | Optional | Whether or not this is a derived portfolio. *(read-only)* |
| **Type** | **string** | Optional | The type of the portfolio. The available values are: Transaction, Reference, DerivedTransaction, SimplePosition |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Properties** | [List&lt;Property&gt;](Property.md) | Optional | The requested portfolio properties. These will be from the &#39;Portfolio&#39; domain. |
| **BaseCurrency** | **string** | Optional | If the portfolio is a transaction portfolio or derived transaction portfolio, this is the base currency of the portfolio. |
| **SubHoldingKeys** | **List&lt;string&gt;** | Optional | The sub holding key properties configured for the portfolio |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CompletePortfolio(
    id: new ResourceId(...),  // required
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    description: "...",  // optional — The long form description of the portfolio.
    displayName: "...",  // optional — The name of the portfolio.
    created: DateTimeOffset.Now,  // optional — The effective datetime at which the portfolio was created. No transactions or constituents can be added to the portfolio before this date.
    parentPortfolioId: new ResourceId(...),  // optional
    isDerived: true,  // optional — Whether or not this is a derived portfolio.
    type: "...",  // optional — The type of the portfolio. The available values are: Transaction, Reference, DerivedTransaction, SimplePosition
    varVersion: new ModelVersion(...),  // required
    properties: new List<Property>(),  // optional — The requested portfolio properties. These will be from the &#39;Portfolio&#39; domain.
    baseCurrency: "...",  // optional — If the portfolio is a transaction portfolio or derived transaction portfolio, this is the base currency of the portfolio.
    subHoldingKeys: ,  // optional — The sub holding key properties configured for the portfolio
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CompletePortfolio>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ModelVersion](ModelVersion.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

