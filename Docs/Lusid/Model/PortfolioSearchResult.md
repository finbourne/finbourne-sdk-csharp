# Finbourne.Sdk.Lusid.Model.PortfolioSearchResult

A list of portfolios.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Type** | **string** | Required | The type of the portfolio. The available values are: Transaction, Reference, DerivedTransaction, SimplePosition |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Description** | **string** | Optional | The long form description of the portfolio. |
| **DisplayName** | **string** | Required | The name of the portfolio. |
| **IsDerived** | **bool** | Optional | Whether or not this is a derived portfolio. *(read-only)* |
| **Created** | **DateTimeOffset** | Required | The effective datetime at which the portfolio was created. No transactions or constituents can be added to the portfolio before this date. |
| **ParentPortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **BaseCurrency** | **string** | Optional | The base currency of the portfolio. |
| **Properties** | [List&lt;Property&gt;](Property.md) | Optional | The requested portfolio properties. These will be from the &#39;Portfolio&#39; domain. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioSearchResult(
    id: new ResourceId(...),  // required
    type: "...",  // required — The type of the portfolio. The available values are: Transaction, Reference, DerivedTransaction, SimplePosition
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    description: "...",  // optional — The long form description of the portfolio.
    displayName: "...",  // required — The name of the portfolio.
    isDerived: true,  // optional — Whether or not this is a derived portfolio.
    created: DateTimeOffset.Now,  // required — The effective datetime at which the portfolio was created. No transactions or constituents can be added to the portfolio before this date.
    parentPortfolioId: new ResourceId(...),  // optional
    baseCurrency: "...",  // optional — The base currency of the portfolio.
    properties: new List<Property>(),  // optional — The requested portfolio properties. These will be from the &#39;Portfolio&#39; domain.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioSearchResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

