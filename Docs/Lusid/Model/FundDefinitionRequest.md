# Finbourne.Sdk.Lusid.Model.FundDefinitionRequest

The request used to create a Fund.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code given for the Fund. |
| **ShortCode** | **string** | Optional | A short code for the Fund. A fund structure tags journal entry lines with the short code of the member they originated from, so it should be unique across the funds of one structure. Optional. |
| **DisplayName** | **string** | Required | The name of the Fund. |
| **Description** | **string** | Optional | A description for the Fund. |
| **BaseCurrency** | **string** | Required | The base currency of the Fund in ISO 4217 currency code format. All portfolios must be of a matching base currency. |
| **InvestorStructure** | **string** | Optional | The Investor structure to be used by the Fund. Available values: NonUnitised, Classes. |
| **PortfolioIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | A list of the Portfolio IDs associated with the fund, which are part of the Fund. Note: These must all have the same base currency, which must also match the Fund Base Currency. |
| **FundConfigurationId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ShareClassInstrumentScopes** | **List&lt;string&gt;** | Optional | The scopes in which the instruments lie, currently limited to one. |
| **ShareClassInstruments** | [List&lt;InstrumentResolutionDetail&gt;](InstrumentResolutionDetail.md) | Optional | Details the user-provided instrument identifiers and the instrument resolved from them. These would be decommissioned in favour of the new AllocationGroups and ShareClasses structures. |
| **Type** | **string** | Optional | The kind of vehicle the fund is, one of the values of the system/fundVehicleType data type. Master and Feeder are deprecated: the structural role of a fund now lives on its fund structure node, and a fund with either type cannot be a member of a fund structure. Available values: Standalone, Master, Feeder, SPV, AIV, TaxBlocker, CarryVehicle, SponsorCommitmentVehicle, CoInvestVehicle, GPInterestHolder, SMA, CTA. |
| **TaxTransparency** | **string** | Optional | Whether the Fund is looked through for tax: Transparent passes its income and gains to its holders as their own, Opaque is taxed in its own right. Optional; if not set, a TaxBlocker is Opaque and a CarryVehicle or GPInterestHolder is Transparent. A fund structure requires it on every SPV and AIV member. Available values: Transparent, Opaque. |
| **InceptionDate** | **DateTimeOffset** | Required | Inception date of the Fund |
| **DecimalPlaces** | **int?** | Optional | Number of decimal places for reporting |
| **PrimaryNavType** | [NavTypeDefinition](NavTypeDefinition.md) | Required | *No description available.* |
| **AdditionalNavTypes** | [List&lt;NavTypeDefinition&gt;](NavTypeDefinition.md) | Optional | The definitions for any additional NAVs on the Fund. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Fund. |
| **CreateInstrument** | **bool** | Optional | Whether to create instruments for the Fund&#39;s share classes, series, or partner classes upon creation. Defaults to false. |
| **ShareClasses** | [List&lt;ShareClassDefinition&gt;](ShareClassDefinition.md) | Optional | An optional list of Share Class definitions for the Fund. |
| **PricingMethodology** | [PricingMethodology](PricingMethodology.md) | Optional | *No description available.* |
| **ReportingPrices** | [List&lt;ReportingPrice&gt;](ReportingPrice.md) | Optional | Share class prices the Fund publishes at each valuation point under labels of its own, alongside the dealing price, for example a mid price for performance reporting. Optional. Each source other than Mid must be published by the valuation recipe of every active NAV type. Labels must be unique and cannot be dealingPrice, dealingBid or dealingOffer. Patch the list whole at /reportingPrices. |
| **WhtParameters** | [WhtParameters](WhtParameters.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundDefinitionRequest(
    code: "...",  // required — The code given for the Fund.
    shortCode: "...",  // optional — A short code for the Fund. A fund structure tags journal entry lines with the short code of the member they originated from, so it should be unique across the funds of one structure. Optional.
    displayName: "...",  // required — The name of the Fund.
    description: "...",  // optional — A description for the Fund.
    baseCurrency: "...",  // required — The base currency of the Fund in ISO 4217 currency code format. All portfolios must be of a matching base currency.
    investorStructure: "...",  // optional — The Investor structure to be used by the Fund. Available values: NonUnitised, Classes.
    portfolioIds: new List<PortfolioEntityId>(),  // required — A list of the Portfolio IDs associated with the fund, which are part of the Fund. Note: These must all have the same base currency, which must also match the Fund Base Currency.
    fundConfigurationId: new ResourceId(...),  // required
    shareClassInstrumentScopes: ,  // optional — The scopes in which the instruments lie, currently limited to one.
    shareClassInstruments: new List<InstrumentResolutionDetail>(),  // optional — Details the user-provided instrument identifiers and the instrument resolved from them. These would be decommissioned in favour of the new AllocationGroups and ShareClasses structures.
    type: "...",  // optional — The kind of vehicle the fund is, one of the values of the system/fundVehicleType data type. Master and Feeder are deprecated: the structural role of a fund now lives on its fund structure node, and a fund with either type cannot be a member of a fund structure. Available values: Standalone, Master, Feeder, SPV, AIV, TaxBlocker, CarryVehicle, SponsorCommitmentVehicle, CoInvestVehicle, GPInterestHolder, SMA, CTA.
    taxTransparency: "...",  // optional — Whether the Fund is looked through for tax: Transparent passes its income and gains to its holders as their own, Opaque is taxed in its own right. Optional; if not set, a TaxBlocker is Opaque and a CarryVehicle or GPInterestHolder is Transparent. A fund structure requires it on every SPV and AIV member. Available values: Transparent, Opaque.
    inceptionDate: DateTimeOffset.Now,  // required — Inception date of the Fund
    decimalPlaces: 0,  // optional — Number of decimal places for reporting
    primaryNavType: new NavTypeDefinition(...),  // required
    additionalNavTypes: new List<NavTypeDefinition>(),  // optional — The definitions for any additional NAVs on the Fund.
    properties: new Property(...),  // optional — A set of properties for the Fund.
    createInstrument: true,  // optional — Whether to create instruments for the Fund&#39;s share classes, series, or partner classes upon creation. Defaults to false.
    shareClasses: new List<ShareClassDefinition>(),  // optional — An optional list of Share Class definitions for the Fund.
    pricingMethodology: new PricingMethodology(...),  // optional
    reportingPrices: new List<ReportingPrice>(),  // optional — Share class prices the Fund publishes at each valuation point under labels of its own, alongside the dealing price, for example a mid price for performance reporting. Optional. Each source other than Mid must be published by the valuation recipe of every active NAV type. Labels must be unique and cannot be dealingPrice, dealingBid or dealingOffer. Patch the list whole at /reportingPrices.
    whtParameters: new WhtParameters(...)  // optional
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
- [PricingMethodology](PricingMethodology.md)
- [ReportingPrice](ReportingPrice.md) — used in `ReportingPrices`
- [WhtParameters](WhtParameters.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

