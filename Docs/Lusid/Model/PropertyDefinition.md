# Finbourne.Sdk.Lusid.Model.PropertyDefinition

A list of property definitions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Key** | **string** | Optional | The property key which uniquely identifies the property. The format for the property key is {domain}/{scope}/{code}, e.g. &#39;Portfolio/Manager/Id&#39;. |
| **ValueType** | **string** | Optional | The type of values that can be associated with this property. This is defined by the property&#39;s data type. The available values are: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText |
| **DisplayName** | **string** | Optional | The display name of the property. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Type** | **string** | Optional | The type of the property. The available values are: Label, Metric, Information |
| **UnitSchema** | **string** | Optional | The units that can be associated with the property&#39;s values. This is defined by the property&#39;s data type. The available values are: NoUnits, Basic, Iso4217Currency |
| **Domain** | **string** | Optional | The domain that the property exists in. The available values are: NotDefined, Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, CutLabelDefinition, Analytic, PortfolioGroup, Person, AccessMetadata, Order, UnitResult, MarketData, ConfigurationRecipe, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, NextBestAction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, AddressKeyDefinition, AmortisationRuleSet, AnalyticsSetInventory, AtomUnitResult, CleardownModule, ComplexMarketData, ComplianceRunSummary, ComplianceRule, ComplianceRunInfo, CorporateActionSource, CounterpartyAgreement, CustomEntityDefinition, DataType, Dialect, EventHandler, GeneralLedgerProfile, PostingModule, Quote, RecipeComposer, ReconciliationRunBreak, ReferenceList, RelationDefinition, ReturnBlockIndex, SRSDocument, SRSIndex, TransactionTemplate, TransactionTemplateScope, TransactionType, TransactionTypeConfig, TranslationScript, TaskDefinition, TaskInstance, Worker, StagingRuleSet, IdentifierDefinition, SettlementInstruction, TransactionFee |
| **Scope** | **string** | Optional | The scope that the property exists in. *(read-only)* |
| **Code** | **string** | Optional | The code of the property. Together with the domain and scope this uniquely identifies the property. *(read-only)* |
| **ValueRequired** | **bool** | Optional | This field is not implemented and should be disregarded. |
| **LifeTime** | **string** | Optional | Describes how the property&#39;s values can change over time. The available values are: Perpetual, TimeVariant |
| **ConstraintStyle** | **string** | Optional | Describes the uniqueness and cardinality of the property for entity objects under the property domain specified in Key. |
| **PropertyDefinitionType** | **string** | Optional | The definition type (DerivedDefinition or Definition). The available values are: ValueProperty, DerivedDefinition |
| **PropertyDescription** | **string** | Optional | A brief description of what a property of this property definition contains. |
| **DerivationFormula** | **string** | Optional | The rule that defines how data is composed for a derived property. |
| **CollectionType** | **string** | Optional | Describes whether a collection property should behave as a set or as an array. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Set of unique property definition properties and associated values to store with the property definition. Each property must be from the &#39;PropertyDefinition&#39; domain. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **IsFilterable** | **bool** | Optional | Bool indicating whether the values of this property are fitlerable, this is true for all non-derived property defintions.  For a derived definition this must be set true to enable filtering. |
| **CustomEntityTypes** | **List&lt;string&gt;** | Optional | The custom entity types that properties relating to this property definition can be applied to. |
| **ValueFormat** | **string** | Optional | The format in which values for this property definition should be represented. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyDefinition(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    key: "...",  // optional — The property key which uniquely identifies the property. The format for the property key is {domain}/{scope}/{code}, e.g. &#39;Portfolio/Manager/Id&#39;.
    valueType: "...",  // optional — The type of values that can be associated with this property. This is defined by the property&#39;s data type. The available values are: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText
    displayName: "...",  // optional — The display name of the property.
    dataTypeId: new ResourceId(...),  // optional
    type: "...",  // optional — The type of the property. The available values are: Label, Metric, Information
    unitSchema: "...",  // optional — The units that can be associated with the property&#39;s values. This is defined by the property&#39;s data type. The available values are: NoUnits, Basic, Iso4217Currency
    domain: "...",  // optional — The domain that the property exists in. The available values are: NotDefined, Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, CutLabelDefinition, Analytic, PortfolioGroup, Person, AccessMetadata, Order, UnitResult, MarketData, ConfigurationRecipe, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, NextBestAction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, AddressKeyDefinition, AmortisationRuleSet, AnalyticsSetInventory, AtomUnitResult, CleardownModule, ComplexMarketData, ComplianceRunSummary, ComplianceRule, ComplianceRunInfo, CorporateActionSource, CounterpartyAgreement, CustomEntityDefinition, DataType, Dialect, EventHandler, GeneralLedgerProfile, PostingModule, Quote, RecipeComposer, ReconciliationRunBreak, ReferenceList, RelationDefinition, ReturnBlockIndex, SRSDocument, SRSIndex, TransactionTemplate, TransactionTemplateScope, TransactionType, TransactionTypeConfig, TranslationScript, TaskDefinition, TaskInstance, Worker, StagingRuleSet, IdentifierDefinition, SettlementInstruction, TransactionFee
    scope: "...",  // optional — The scope that the property exists in.
    code: "...",  // optional — The code of the property. Together with the domain and scope this uniquely identifies the property.
    valueRequired: true,  // optional — This field is not implemented and should be disregarded.
    lifeTime: "...",  // optional — Describes how the property&#39;s values can change over time. The available values are: Perpetual, TimeVariant
    constraintStyle: "...",  // optional — Describes the uniqueness and cardinality of the property for entity objects under the property domain specified in Key.
    propertyDefinitionType: "...",  // optional — The definition type (DerivedDefinition or Definition). The available values are: ValueProperty, DerivedDefinition
    propertyDescription: "...",  // optional — A brief description of what a property of this property definition contains.
    derivationFormula: "...",  // optional — The rule that defines how data is composed for a derived property.
    collectionType: "...",  // optional — Describes whether a collection property should behave as a set or as an array.
    properties: new Property(...),  // optional — Set of unique property definition properties and associated values to store with the property definition. Each property must be from the &#39;PropertyDefinition&#39; domain.
    varVersion: new ModelVersion(...),  // optional
    stagedModifications: new StagedModificationsInfo(...),  // optional
    isFilterable: true,  // optional — Bool indicating whether the values of this property are fitlerable, this is true for all non-derived property defintions.  For a derived definition this must be set true to enable filtering.
    customEntityTypes: ,  // optional — The custom entity types that properties relating to this property definition can be applied to.
    valueFormat: "...",  // optional — The format in which values for this property definition should be represented.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyDefinition>(json);
```

- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

