# Finbourne.Sdk.Lusid.Model.CreateDerivedPropertyDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Domain** | **string** | Required | The domain that the property exists in. Not all available values are currently supported, please check the documentation: https://support.lusid.com/knowledgebase/article/KA-01719/. The available values are: NotDefined, Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, CutLabelDefinition, Analytic, PortfolioGroup, Person, AccessMetadata, Order, UnitResult, MarketData, ConfigurationRecipe, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, NextBestAction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, AddressKeyDefinition, AmortisationRuleSet, AnalyticsSetInventory, AtomUnitResult, CleardownModule, ComplexMarketData, ComplianceRunSummary, ComplianceRule, ComplianceRunInfo, CorporateActionSource, CounterpartyAgreement, CustomEntityDefinition, DataType, Dialect, EventHandler, GeneralLedgerProfile, PostingModule, Quote, RecipeComposer, ReconciliationRunBreak, ReferenceList, RelationDefinition, ReturnBlockIndex, SRSDocument, SRSIndex, TransactionTemplate, TransactionTemplateScope, TransactionType, TransactionTypeConfig, TranslationScript, TaskDefinition, TaskInstance, Worker, StagingRuleSet, IdentifierDefinition, SettlementInstruction, TransactionFee |
| **Scope** | **string** | Required | The scope that the property exists in. |
| **Code** | **string** | Required | The code of the property. Together with the domain and scope this uniquely identifies the property. |
| **DisplayName** | **string** | Required | The display name of the property. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PropertyDescription** | **string** | Optional | Describes the property |
| **DerivationFormula** | **string** | Required | The rule that defines how data is composed for a derived property. |
| **IsFilterable** | **bool** | Required | Bool indicating whether the values of this property are fitlerable, this is true for all non-derived property defintions.  For a derived definition this must be set true to enable filtering. |
| **ValueFormat** | **string** | Optional | The format in which values for this property definition should be represented. |
| **CustomEntityType** | **string** | Optional | The custom entity type that this derived property definition can be applied to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateDerivedPropertyDefinitionRequest(
    domain: "...",  // required — The domain that the property exists in. Not all available values are currently supported, please check the documentation: https://support.lusid.com/knowledgebase/article/KA-01719/. The available values are: NotDefined, Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, CutLabelDefinition, Analytic, PortfolioGroup, Person, AccessMetadata, Order, UnitResult, MarketData, ConfigurationRecipe, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, NextBestAction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, AddressKeyDefinition, AmortisationRuleSet, AnalyticsSetInventory, AtomUnitResult, CleardownModule, ComplexMarketData, ComplianceRunSummary, ComplianceRule, ComplianceRunInfo, CorporateActionSource, CounterpartyAgreement, CustomEntityDefinition, DataType, Dialect, EventHandler, GeneralLedgerProfile, PostingModule, Quote, RecipeComposer, ReconciliationRunBreak, ReferenceList, RelationDefinition, ReturnBlockIndex, SRSDocument, SRSIndex, TransactionTemplate, TransactionTemplateScope, TransactionType, TransactionTypeConfig, TranslationScript, TaskDefinition, TaskInstance, Worker, StagingRuleSet, IdentifierDefinition, SettlementInstruction, TransactionFee
    scope: "...",  // required — The scope that the property exists in.
    code: "...",  // required — The code of the property. Together with the domain and scope this uniquely identifies the property.
    displayName: "...",  // required — The display name of the property.
    dataTypeId: new ResourceId(...),  // required
    propertyDescription: "...",  // optional — Describes the property
    derivationFormula: "...",  // required — The rule that defines how data is composed for a derived property.
    isFilterable: true,  // required — Bool indicating whether the values of this property are fitlerable, this is true for all non-derived property defintions.  For a derived definition this must be set true to enable filtering.
    valueFormat: "...",  // optional — The format in which values for this property definition should be represented.
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

