# Finbourne.Sdk.Lusid.Model.CreatePropertyDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Domain** | **string** | Required | The domain that the property exists in. The available values are: NotDefined, Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, CutLabelDefinition, Analytic, PortfolioGroup, Person, AccessMetadata, Order, UnitResult, MarketData, ConfigurationRecipe, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, NextBestAction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, AddressKeyDefinition, AmortisationRuleSet, AnalyticsSetInventory, AtomUnitResult, CleardownModule, ComplexMarketData, ComplianceRunSummary, ComplianceRule, ComplianceRunInfo, CorporateActionSource, CounterpartyAgreement, CustomEntityDefinition, DataType, Dialect, EventHandler, GeneralLedgerProfile, PostingModule, Quote, RecipeComposer, ReconciliationRunBreak, ReferenceList, RelationDefinition, ReturnBlockIndex, SRSDocument, SRSIndex, TransactionTemplate, TransactionTemplateScope, TransactionType, TransactionTypeConfig, TranslationScript, TaskDefinition, TaskInstance, Worker, StagingRuleSet, IdentifierDefinition, SettlementInstruction, TransactionFee |
| **Scope** | **string** | Required | The scope that the property exists in. |
| **Code** | **string** | Required | The code of the property. Together with the domain and scope this uniquely identifies the property. |
| **ValueRequired** | **bool** | Optional | This field is not implemented and should be disregarded. |
| **DisplayName** | **string** | Required | The display name of the property. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **LifeTime** | **string** | Optional | Describes how the property&#39;s values can change over time. The available values are: Perpetual, TimeVariant |
| **ConstraintStyle** | **string** | Optional | Describes the uniqueness and cardinality of the property for entity objects under the property domain specified in Key. Defaults to \&quot;Property\&quot; if not specified. Valid values for this field are: Property, Collection or Identifier. |
| **PropertyDescription** | **string** | Optional | Describes the property |
| **CollectionType** | **string** | Optional | Describes whether a collection property should behave as a set or as an array. |
| **CustomEntityTypes** | **List&lt;string&gt;** | Optional | The custom entity types that properties relating to this property definition can be applied to. |
| **ValueFormat** | **string** | Optional | The format in which values for this property definition should be represented. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreatePropertyDefinitionRequest(
    domain: "...",  // required — The domain that the property exists in. The available values are: NotDefined, Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, CutLabelDefinition, Analytic, PortfolioGroup, Person, AccessMetadata, Order, UnitResult, MarketData, ConfigurationRecipe, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, NextBestAction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, AddressKeyDefinition, AmortisationRuleSet, AnalyticsSetInventory, AtomUnitResult, CleardownModule, ComplexMarketData, ComplianceRunSummary, ComplianceRule, ComplianceRunInfo, CorporateActionSource, CounterpartyAgreement, CustomEntityDefinition, DataType, Dialect, EventHandler, GeneralLedgerProfile, PostingModule, Quote, RecipeComposer, ReconciliationRunBreak, ReferenceList, RelationDefinition, ReturnBlockIndex, SRSDocument, SRSIndex, TransactionTemplate, TransactionTemplateScope, TransactionType, TransactionTypeConfig, TranslationScript, TaskDefinition, TaskInstance, Worker, StagingRuleSet, IdentifierDefinition, SettlementInstruction, TransactionFee
    scope: "...",  // required — The scope that the property exists in.
    code: "...",  // required — The code of the property. Together with the domain and scope this uniquely identifies the property.
    valueRequired: true,  // optional — This field is not implemented and should be disregarded.
    displayName: "...",  // required — The display name of the property.
    dataTypeId: new ResourceId(...),  // required
    lifeTime: "...",  // optional — Describes how the property&#39;s values can change over time. The available values are: Perpetual, TimeVariant
    constraintStyle: "...",  // optional — Describes the uniqueness and cardinality of the property for entity objects under the property domain specified in Key. Defaults to \&quot;Property\&quot; if not specified. Valid values for this field are: Property, Collection or Identifier.
    propertyDescription: "...",  // optional — Describes the property
    collectionType: "...",  // optional — Describes whether a collection property should behave as a set or as an array.
    customEntityTypes: ,  // optional — The custom entity types that properties relating to this property definition can be applied to.
    valueFormat: "..."  // optional — The format in which values for this property definition should be represented.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreatePropertyDefinitionRequest>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

