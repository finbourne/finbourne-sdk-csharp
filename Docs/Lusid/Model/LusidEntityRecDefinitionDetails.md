# Finbourne.Sdk.Lusid.Model.LusidEntityRecDefinitionDetails

A definition that reconciles one type of LUSID entity. A filter selects the population of each side, and a single  matching ruleset of that entity type drives the definition.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The type of LUSID entity to reconcile, which is also the rec type of the results. Supported types: Instrument, LegalEntity, Portfolio. A custom entity type is written as its name, which starts with ~. Must equal the reconciliationType of the matching ruleset. Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity, External, Instrument, LegalEntity, Portfolio. |
| **MatchingRulesetId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **LeftFilter** | **string** | Optional | Optional filter that selects the population of the left side. It uses the filter syntax of the list endpoint of the entity type. Null reads the whole population of the side. |
| **RightFilter** | **string** | Optional | Optional filter that selects the population of the right side. It uses the filter syntax of the list endpoint of the entity type. Null reads the whole population of the side. |
| **DefinitionType** | **string** | Required | What this definition reconciles, and so which shape of details it carries. Available values: PortfolioContents, LusidEntity, External. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LusidEntityRecDefinitionDetails(
    entityType: "...",  // required — The type of LUSID entity to reconcile, which is also the rec type of the results. Supported types: Instrument, LegalEntity, Portfolio. A custom entity type is written as its name, which starts with ~. Must equal the reconciliationType of the matching ruleset. Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity, External, Instrument, LegalEntity, Portfolio.
    matchingRulesetId: new ResourceId(...),  // required
    leftFilter: "...",  // optional — Optional filter that selects the population of the left side. It uses the filter syntax of the list endpoint of the entity type. Null reads the whole population of the side.
    rightFilter: "...",  // optional — Optional filter that selects the population of the right side. It uses the filter syntax of the list endpoint of the entity type. Null reads the whole population of the side.
    definitionType: "..."  // required — What this definition reconciles, and so which shape of details it carries. Available values: PortfolioContents, LusidEntity, External.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidEntityRecDefinitionDetails>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

