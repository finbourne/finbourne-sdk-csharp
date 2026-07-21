# Finbourne.Sdk.Lusid.Model.IdentifierDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Domain** | **string** | Required | The type of entity to which the identifier can be attached. Available values: Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, PortfolioGroup, Person, Order, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, TaskDefinition, Workflow, IdentifierDefinition, SettlementInstruction, TransactionFeeType, PaymentInstruction. |
| **IdentifierScope** | **string** | Required | The scope that the identifier definition exists in. |
| **IdentifierType** | **string** | Required | What the identifier represents. Together with \&quot;domain\&quot; and \&quot;identifierScope\&quot; this uniquely identifies the identifier definition. |
| **LifeTime** | **string** | Required | Describes whether an identifier value is associated with an entity for all effective dates or applies within a specified effective date range. Available values: Perpetual, TimeVariant. |
| **HierarchyUsage** | **string** | Optional | MasterIdentifier (aka unique)  An entity can have one value for this identifier definition on a given effective date.  A value for this identifier definition can only be associated with one entity (in a given scope) on a given effective date.  ParentIdentifier (aka non-unique)  An entity can have one value for this identifier definition on a given effective date.  A value for this identifier definition can be associated with many entities (in a given scope) on a given effective date.  Default value: MasterIdentifier. Available values: MasterIdentifier, ParentIdentifier. |
| **HierarchyLevel** | **string** | Optional | Optional metadata associated with the identifier definition. |
| **DisplayName** | **string** | Optional | A display name for the identifier. E.g. Figi. |
| **Description** | **string** | Optional | An optional description for the identifier. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the identifier definition. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IdentifierDefinition(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    domain: "...",  // required — The type of entity to which the identifier can be attached. Available values: Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, PortfolioGroup, Person, Order, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, TaskDefinition, Workflow, IdentifierDefinition, SettlementInstruction, TransactionFeeType, PaymentInstruction.
    identifierScope: "...",  // required — The scope that the identifier definition exists in.
    identifierType: "...",  // required — What the identifier represents. Together with \&quot;domain\&quot; and \&quot;identifierScope\&quot; this uniquely identifies the identifier definition.
    lifeTime: "...",  // required — Describes whether an identifier value is associated with an entity for all effective dates or applies within a specified effective date range. Available values: Perpetual, TimeVariant.
    hierarchyUsage: "...",  // optional — MasterIdentifier (aka unique)  An entity can have one value for this identifier definition on a given effective date.  A value for this identifier definition can only be associated with one entity (in a given scope) on a given effective date.  ParentIdentifier (aka non-unique)  An entity can have one value for this identifier definition on a given effective date.  A value for this identifier definition can be associated with many entities (in a given scope) on a given effective date.  Default value: MasterIdentifier. Available values: MasterIdentifier, ParentIdentifier.
    hierarchyLevel: "...",  // optional — Optional metadata associated with the identifier definition.
    displayName: "...",  // optional — A display name for the identifier. E.g. Figi.
    description: "...",  // optional — An optional description for the identifier.
    properties: new Property(...),  // optional — A set of properties for the identifier definition.
    varVersion: new ModelVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IdentifierDefinition>(json);
```

- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

