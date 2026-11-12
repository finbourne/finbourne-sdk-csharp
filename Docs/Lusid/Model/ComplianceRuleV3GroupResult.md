# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3GroupResult

The result of one rule for a single evaluated group: its status, the group key identifying it, the  measured value, the unit the value and limits are expressed in, the limits it was checked against, the  portfolios and orders it affects, and, when it could not be assessed, the missing-data details.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Optional | Available values: Passed, Failed, Warning, MissingData. |
| **GroupKey** | **string** | Optional | *No description available.* |
| **MeasuredValue** | **decimal?** | Optional | *No description available.* |
| **HardLimit** | **decimal?** | Optional | *No description available.* |
| **SoftLimit** | **decimal?** | Optional | *No description available.* |
| **Unit** | **string** | Optional | Available values: Absolute, Percentage. |
| **AffectedPortfolioIds** | **List&lt;string&gt;** | Optional | *No description available.* |
| **AffectedOrderIds** | **List&lt;string&gt;** | Optional | *No description available.* |
| **MissingDataDetails** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3GroupResult(
    status: "...",  // optional — Available values: Passed, Failed, Warning, MissingData.
    groupKey: "...",  // optional
    measuredValue: 0.0d,  // optional
    hardLimit: 0.0d,  // optional
    softLimit: 0.0d,  // optional
    unit: "...",  // optional — Available values: Absolute, Percentage.
    affectedPortfolioIds: ,  // optional
    affectedOrderIds: ,  // optional
    missingDataDetails:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3GroupResult>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

