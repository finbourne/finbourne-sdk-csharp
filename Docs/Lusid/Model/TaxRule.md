# Finbourne.Sdk.Lusid.Model.TaxRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | A user-friendly name |
| **Description** | **string** | Required | A description for this rule |
| **Rate** | **decimal** | Required | The rate to be applied if all criteria are met |
| **MatchCriteria** | [List&lt;MatchCriterion&gt;](MatchCriterion.md) | Required | A set of criteria to be met for this rule to be applied |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxRule(
    name: "...",  // required — A user-friendly name
    description: "...",  // required — A description for this rule
    rate: 0.0d,  // required — The rate to be applied if all criteria are met
    matchCriteria: new List<MatchCriterion>()  // required — A set of criteria to be met for this rule to be applied
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxRule>(json);
```

- [MatchCriterion](MatchCriterion.md) — used in `MatchCriteria`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

