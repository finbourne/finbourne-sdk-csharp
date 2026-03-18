# Finbourne.Sdk.Lusid.Model.DataQualityCheckResult

Represents the result of a data quality check operation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CheckDefinitionScope** | **string** | Optional | The scope of the check definition |
| **CheckDefinitionCode** | **string** | Optional | The code of the check definition |
| **CheckDefinitionDisplayName** | **string** | Optional | The display name of the check definition |
| **CheckRunAsAt** | **DateTimeOffset** | Optional | The timestamp when the check was run |
| **ResultType** | **string** | Optional | The type of result from the check |
| **RuleSetKey** | **string** | Optional | The key identifying the ruleset |
| **RuleSetDisplayName** | **string** | Optional | The display name of the ruleset |
| **RuleKey** | **string** | Optional | The key identifying the rule (for RuleInvalid, RuleBreached, RuleBreachesOverLimit) |
| **RuleDisplayName** | **string** | Optional | The display name of the rule (for RuleInvalid, RuleBreached, RuleBreachesOverLimit) |
| **RuleDescription** | **string** | Optional | The description of the rule (for RuleInvalid, RuleBreached, RuleBreachesOverLimit) |
| **RuleFormula** | **string** | Optional | The formula of the rule (for RuleInvalid, RuleBreached, RuleBreachesOverLimit) |
| **Severity** | **int?** | Optional | The severity level |
| **LusidEntity** | [LusidEntityResult](LusidEntityResult.md) | Optional | *No description available.* |
| **CountRuleBreaches** | **int?** | Optional | The count of rule breaches (1 for RuleBreached, multiple for RuleBreachesOverLimit) |
| **ErrorDetail** | **string** | Optional | Error details (for RulesetInvalid, RuleInvalid) |
| **ResultId** | **string** | Optional | Unique identifier for the result in format: {{GUID of Check Definition}}-{{resultType}}-{{rulesetKey}}-{{ruleKey}}-{{entity GUID}} |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DataQualityCheckResult(
    checkDefinitionScope: "...",  // optional — The scope of the check definition
    checkDefinitionCode: "...",  // optional — The code of the check definition
    checkDefinitionDisplayName: "...",  // optional — The display name of the check definition
    checkRunAsAt: DateTimeOffset.Now,  // optional — The timestamp when the check was run
    resultType: "...",  // optional — The type of result from the check
    ruleSetKey: "...",  // optional — The key identifying the ruleset
    ruleSetDisplayName: "...",  // optional — The display name of the ruleset
    ruleKey: "...",  // optional — The key identifying the rule (for RuleInvalid, RuleBreached, RuleBreachesOverLimit)
    ruleDisplayName: "...",  // optional — The display name of the rule (for RuleInvalid, RuleBreached, RuleBreachesOverLimit)
    ruleDescription: "...",  // optional — The description of the rule (for RuleInvalid, RuleBreached, RuleBreachesOverLimit)
    ruleFormula: "...",  // optional — The formula of the rule (for RuleInvalid, RuleBreached, RuleBreachesOverLimit)
    severity: 0,  // optional — The severity level
    lusidEntity: new LusidEntityResult(...),  // optional
    countRuleBreaches: 0,  // optional — The count of rule breaches (1 for RuleBreached, multiple for RuleBreachesOverLimit)
    errorDetail: "...",  // optional — Error details (for RulesetInvalid, RuleInvalid)
    resultId: "..."  // optional — Unique identifier for the result in format: {{GUID of Check Definition}}-{{resultType}}-{{rulesetKey}}-{{ruleKey}}-{{entity GUID}}
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DataQualityCheckResult>(json);
```

- [LusidEntityResult](LusidEntityResult.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

