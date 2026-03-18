# Finbourne.Sdk.Lusid.Model.Fund

A Fund entity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Fund. |
| **Description** | **string** | Optional | A description for the Fund. |
| **BaseCurrency** | **string** | Optional | The base currency of the Fund in ISO 4217 currency code format. All portfolios must be of a matching base currency. |
| **InvestorStructure** | **string** | Required | The Investor structure to be used by the Fund. Supported values are &#39;NonUnitised&#39; and &#39;Classes&#39;. |
| **PortfolioIds** | [List&lt;PortfolioEntityIdWithDetails&gt;](PortfolioEntityIdWithDetails.md) | Optional | A list of the portfolios on the fund, which are part of the Fund. Note: These must all have the same base currency, which must also much the Fund Base Currency. |
| **FundConfigurationId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **AborId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ShareClassInstruments** | [List&lt;InstrumentResolutionDetail&gt;](InstrumentResolutionDetail.md) | Optional | Details the user-provided instrument identifiers and the instrument resolved from them. |
| **Type** | **string** | Optional | The type of fund; &#39;Standalone&#39;, &#39;Master&#39; or &#39;Feeder&#39; |
| **InceptionDate** | **DateTimeOffset** | Required | Inception date of the Fund |
| **DecimalPlaces** | **int?** | Optional | Number of decimal places for reporting |
| **YearEndDate** | [DayMonth](DayMonth.md) | Optional | *No description available.* |
| **PrimaryNavType** | [NavType](NavType.md) | Optional | *No description available.* |
| **AdditionalNavTypes** | [List&lt;NavType&gt;](NavType.md) | Optional | The definitions for any additional NAVs on the Fund. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Fund. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Fund(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    displayName: "...",  // optional — The name of the Fund.
    description: "...",  // optional — A description for the Fund.
    baseCurrency: "...",  // optional — The base currency of the Fund in ISO 4217 currency code format. All portfolios must be of a matching base currency.
    investorStructure: "...",  // required — The Investor structure to be used by the Fund. Supported values are &#39;NonUnitised&#39; and &#39;Classes&#39;.
    portfolioIds: new List<PortfolioEntityIdWithDetails>(),  // optional — A list of the portfolios on the fund, which are part of the Fund. Note: These must all have the same base currency, which must also much the Fund Base Currency.
    fundConfigurationId: new ResourceId(...),  // optional
    aborId: new ResourceId(...),  // optional
    shareClassInstruments: new List<InstrumentResolutionDetail>(),  // optional — Details the user-provided instrument identifiers and the instrument resolved from them.
    type: "...",  // optional — The type of fund; &#39;Standalone&#39;, &#39;Master&#39; or &#39;Feeder&#39;
    inceptionDate: DateTimeOffset.Now,  // required — Inception date of the Fund
    decimalPlaces: 0,  // optional — Number of decimal places for reporting
    yearEndDate: new DayMonth(...),  // optional
    primaryNavType: new NavType(...),  // optional
    additionalNavTypes: new List<NavType>(),  // optional — The definitions for any additional NAVs on the Fund.
    properties: new Property(...),  // optional — A set of properties for the Fund.
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
var instance = JsonConvert.DeserializeObject<Fund>(json);
```

- [ResourceId](ResourceId.md)
- [PortfolioEntityIdWithDetails](PortfolioEntityIdWithDetails.md) — used in `PortfolioIds`
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [InstrumentResolutionDetail](InstrumentResolutionDetail.md) — used in `ShareClassInstruments`
- [DayMonth](DayMonth.md)
- [NavType](NavType.md)
- [NavType](NavType.md) — used in `AdditionalNavTypes`
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

