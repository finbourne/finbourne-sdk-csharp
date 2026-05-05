# Finbourne.Sdk.Lusid.Model.CreatePropertyDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Domain** | **string** | Required | The domain that the property exists in. Available values: Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, PortfolioGroup, Person, Order, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, IdentifierDefinition, SettlementInstruction, TransactionFee. |
| **Scope** | **string** | Required | The scope that the property exists in. |
| **Code** | **string** | Required | The code of the property. Together with the domain and scope this uniquely identifies the property. |
| **ValueRequired** | **bool** | Optional | This field is not implemented and should be disregarded. |
| **DisplayName** | **string** | Required | The display name of the property. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **LifeTime** | **string** | Optional | Describes how the property&#39;s values can change over time. Available values: Perpetual, TimeVariant. |
| **ConstraintStyle** | **string** | Optional | Describes the uniqueness and cardinality of the property for entity objects under the property domain specified in Key. Defaults to \&quot;Property\&quot; if not specified. Valid values for this field are: Property, Collection or Identifier. |
| **PropertyDescription** | **string** | Optional | Describes the property |
| **CollectionType** | **string** | Optional | Describes whether a collection property should behave as a Set or as an Array. Available values: Set, Array. |
| **CustomEntityTypes** | **List&lt;string&gt;** | Optional | The custom entity types that properties relating to this property definition can be applied to. |
| **ValueFormat** | **string** | Optional | The format in which values for this property definition should be represented. Available values: Text, Html. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreatePropertyDefinitionRequest(
    domain: "...",  // required — The domain that the property exists in. Available values: Transaction, Portfolio, Holding, ReferenceHolding, TransactionConfiguration, Instrument, PortfolioGroup, Person, Order, Allocation, Calendar, LegalEntity, InvestorRecord, InvestmentAccount, Placement, Execution, Block, Participation, Package, OrderInstruction, CustomEntity, InstrumentEvent, Account, ChartOfAccounts, CustodianAccount, CheckDefinition, Abor, AborConfiguration, Fund, FundConfiguration, Fee, Reconciliation, PropertyDefinition, Compliance, DiaryEntry, Leg, DerivedValuation, Timeline, ClosedPeriod, IdentifierDefinition, SettlementInstruction, TransactionFee.
    scope: "...",  // required — The scope that the property exists in.
    code: "...",  // required — The code of the property. Together with the domain and scope this uniquely identifies the property.
    valueRequired: true,  // optional — This field is not implemented and should be disregarded.
    displayName: "...",  // required — The display name of the property.
    dataTypeId: new ResourceId(...),  // required
    lifeTime: "...",  // optional — Describes how the property&#39;s values can change over time. Available values: Perpetual, TimeVariant.
    constraintStyle: "...",  // optional — Describes the uniqueness and cardinality of the property for entity objects under the property domain specified in Key. Defaults to \&quot;Property\&quot; if not specified. Valid values for this field are: Property, Collection or Identifier.
    propertyDescription: "...",  // optional — Describes the property
    collectionType: "...",  // optional — Describes whether a collection property should behave as a Set or as an Array. Available values: Set, Array.
    customEntityTypes: ,  // optional — The custom entity types that properties relating to this property definition can be applied to.
    valueFormat: "..."  // optional — The format in which values for this property definition should be represented. Available values: Text, Html.
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

