# Finbourne.Sdk.Lusid.Model.CreateIdentifierDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Domain** | **string** | Required | The type of entity to which the identifier can be attached. Available values: Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, PortfolioGroup, Person, Order, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, IdentifierDefinition, SettlementInstruction, TransactionFee. |
| **IdentifierScope** | **string** | Required | The scope that the identifier definition exists in. |
| **IdentifierType** | **string** | Required | What the identifier represents. Together with \&quot;domain\&quot; and \&quot;identifierScope\&quot; this uniquely identifies the identifier definition. |
| **LifeTime** | **string** | Required | Describes whether an identifier value is associated with an entity for all effective dates or applies within a specified effective date range. Available values: Perpetual, TimeVariant. |
| **HierarchyUsage** | **string** | Optional | MasterIdentifier (aka unique) An entity can have one value for this identifier definition on a given effective date. A value for this identifier definition can only be associated with one entity (in a given scope) on a given effective date. ParentIdentifier (aka non-unique) An entity can have one value for this identifier definition on a given effective date. A value for this identifier definition can be associated with many entities (in a given scope) on a given effective date. Default value: MasterIdentifier. Available values: MasterIdentifier, ParentIdentifier. |
| **HierarchyLevel** | **string** | Optional | Optional metadata associated with the identifier definition. |
| **DisplayName** | **string** | Optional | A display name for the identifier. E.g. Figi. |
| **Description** | **string** | Optional | An optional description for the identifier. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the identifier definition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateIdentifierDefinitionRequest(
    domain: "...",  // required — The type of entity to which the identifier can be attached. Available values: Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, PortfolioGroup, Person, Order, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, IdentifierDefinition, SettlementInstruction, TransactionFee.
    identifierScope: "...",  // required — The scope that the identifier definition exists in.
    identifierType: "...",  // required — What the identifier represents. Together with \&quot;domain\&quot; and \&quot;identifierScope\&quot; this uniquely identifies the identifier definition.
    lifeTime: "...",  // required — Describes whether an identifier value is associated with an entity for all effective dates or applies within a specified effective date range. Available values: Perpetual, TimeVariant.
    hierarchyUsage: "...",  // optional — MasterIdentifier (aka unique) An entity can have one value for this identifier definition on a given effective date. A value for this identifier definition can only be associated with one entity (in a given scope) on a given effective date. ParentIdentifier (aka non-unique) An entity can have one value for this identifier definition on a given effective date. A value for this identifier definition can be associated with many entities (in a given scope) on a given effective date. Default value: MasterIdentifier. Available values: MasterIdentifier, ParentIdentifier.
    hierarchyLevel: "...",  // optional — Optional metadata associated with the identifier definition.
    displayName: "...",  // optional — A display name for the identifier. E.g. Figi.
    description: "...",  // optional — An optional description for the identifier.
    properties: new Property(...)  // optional — A set of properties for the identifier definition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateIdentifierDefinitionRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

