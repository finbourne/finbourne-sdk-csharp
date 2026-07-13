# Finbourne.Sdk.Lusid.Model.FundDefinitionRequest

The request used to create a Fund.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code given for the Fund. |
| **DisplayName** | **string** | Required | The name of the Fund. |
| **Description** | **string** | Optional | A description for the Fund. |
| **BaseCurrency** | **string** | Required | The base currency of the Fund in ISO 4217 currency code format. All portfolios must be of a matching base currency. |
| **InvestorStructure** | **string** | Optional | The Investor structure to be used by the Fund. Available values: NonUnitised, Classes. |
| **PortfolioIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | A list of the Portfolio IDs associated with the fund, which are part of the Fund. Note: These must all have the same base currency, which must also match the Fund Base Currency. |
| **FundConfigurationId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ShareClassInstrumentScopes** | **List&lt;string&gt;** | Optional | The scopes in which the instruments lie, currently limited to one. |
| **ShareClassInstruments** | [List&lt;InstrumentResolutionDetail&gt;](InstrumentResolutionDetail.md) | Optional | Details the user-provided instrument identifiers and the instrument resolved from them. These would be decommissioned in favour of the new AllocationGroups and ShareClasses structures. |
| **Type** | **string** | Optional | The type of fund. Available values: Standalone, Master, Feeder. |
| **InceptionDate** | **DateTimeOffset** | Required | Inception date of the Fund |
| **DecimalPlaces** | **int?** | Optional | Number of decimal places for reporting |
| **PrimaryNavType** | [NavTypeDefinition](NavTypeDefinition.md) | Required | *No description available.* |
| **AdditionalNavTypes** | [List&lt;NavTypeDefinition&gt;](NavTypeDefinition.md) | Optional | The definitions for any additional NAVs on the Fund. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Fund. |
| **CreateInstrument** | **bool** | Optional | Whether to create instruments for the Fund&#39;s share classes, series, or partner classes upon creation. Defaults to false. |
| **ShareClasses** | [List&lt;ShareClassDefinition&gt;](ShareClassDefinition.md) | Optional | An optional list of Share Class definitions for the Fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundDefinitionRequest(
    code: "...",  // required — The code given for the Fund.
    displayName: "...",  // required — The name of the Fund.
    description: "...",  // optional — A description for the Fund.
    baseCurrency: "...",  // required — The base currency of the Fund in ISO 4217 currency code format. All portfolios must be of a matching base currency.
    investorStructure: "...",  // optional — The Investor structure to be used by the Fund. Available values: NonUnitised, Classes.
    portfolioIds: new List<PortfolioEntityId>(),  // required — A list of the Portfolio IDs associated with the fund, which are part of the Fund. Note: These must all have the same base currency, which must also match the Fund Base Currency.
    fundConfigurationId: new ResourceId(...),  // required
    shareClassInstrumentScopes: ,  // optional — The scopes in which the instruments lie, currently limited to one.
    shareClassInstruments: new List<InstrumentResolutionDetail>(),  // optional — Details the user-provided instrument identifiers and the instrument resolved from them. These would be decommissioned in favour of the new AllocationGroups and ShareClasses structures.
    type: "...",  // optional — The type of fund. Available values: Standalone, Master, Feeder.
    inceptionDate: DateTimeOffset.Now,  // required — Inception date of the Fund
    decimalPlaces: 0,  // optional — Number of decimal places for reporting
    primaryNavType: new NavTypeDefinition(...),  // required
    additionalNavTypes: new List<NavTypeDefinition>(),  // optional — The definitions for any additional NAVs on the Fund.
    properties: new Property(...),  // optional — A set of properties for the Fund.
    createInstrument: true,  // optional — Whether to create instruments for the Fund&#39;s share classes, series, or partner classes upon creation. Defaults to false.
    shareClasses: new List<ShareClassDefinition>()  // optional — An optional list of Share Class definitions for the Fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundDefinitionRequest>(json);
```

- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioIds`
- [ResourceId](ResourceId.md)
- [InstrumentResolutionDetail](InstrumentResolutionDetail.md) — used in `ShareClassInstruments`
- [NavTypeDefinition](NavTypeDefinition.md)
- [NavTypeDefinition](NavTypeDefinition.md) — used in `AdditionalNavTypes`
- [Property](Property.md) — used in `Properties`
- [ShareClassDefinition](ShareClassDefinition.md) — used in `ShareClasses`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

