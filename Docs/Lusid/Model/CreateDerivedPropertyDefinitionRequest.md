# Finbourne.Sdk.Lusid.Model.CreateDerivedPropertyDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Domain** | **string** | Required | The domain that the property exists in. Not all available values are currently supported, please check the documentation: https://support.lusid.com/knowledgebase/article/KA-01719/. Available values: Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, PortfolioGroup, Person, Order, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, IdentifierDefinition, SettlementInstruction, TransactionFeeType. |
| **Scope** | **string** | Required | The scope that the property exists in. |
| **Code** | **string** | Required | The code of the property. Together with the domain and scope this uniquely identifies the property. |
| **DisplayName** | **string** | Required | The display name of the property. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PropertyDescription** | **string** | Optional | Describes the property |
| **DerivationFormula** | **string** | Required | The rule that defines how data is composed for a derived property. |
| **IsFilterable** | **bool** | Required | Bool indicating whether the values of this property are fitlerable, this is true for all non-derived property defintions.  For a derived definition this must be set true to enable filtering. |
| **ValueFormat** | **string** | Optional | The format in which values for this property definition should be represented. Available values: Text, Html. |
| **CustomEntityType** | **string** | Optional | The custom entity type that this derived property definition can be applied to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateDerivedPropertyDefinitionRequest(
    domain: "...",  // required — The domain that the property exists in. Not all available values are currently supported, please check the documentation: https://support.lusid.com/knowledgebase/article/KA-01719/. Available values: Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, PortfolioGroup, Person, Order, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, IdentifierDefinition, SettlementInstruction, TransactionFeeType.
    scope: "...",  // required — The scope that the property exists in.
    code: "...",  // required — The code of the property. Together with the domain and scope this uniquely identifies the property.
    displayName: "...",  // required — The display name of the property.
    dataTypeId: new ResourceId(...),  // required
    propertyDescription: "...",  // optional — Describes the property
    derivationFormula: "...",  // required — The rule that defines how data is composed for a derived property.
    isFilterable: true,  // required — Bool indicating whether the values of this property are fitlerable, this is true for all non-derived property defintions.  For a derived definition this must be set true to enable filtering.
    valueFormat: "...",  // optional — The format in which values for this property definition should be represented. Available values: Text, Html.
    customEntityType: "..."  // optional — The custom entity type that this derived property definition can be applied to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateDerivedPropertyDefinitionRequest>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

