# Finbourne.Sdk.Lusid.Model.ComplianceRunInfo

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Required | The unique identifier of a compliance run |
| **InstigatedAt** | **DateTimeOffset** | Required | The time the compliance run was launched (e.g. button pressed). Currently it is also both the as at and effective at time in whichthe rule set and portfolio data (including any pending trades if the run is pretrade) is taken for the caluation, although it may be possible to run compliance for historical effective at and as at dates in the future. |
| **CompletedAt** | **DateTimeOffset** | Required | The time the compliance run calculation was completed |
| **Schedule** | **string** | Required | Whether the compliance run was pre or post trade |
| **AllRulesPassed** | **bool** | Required | True if all rules passed, for all the portfolios they were assigned to |
| **HasResults** | **bool** | Required | False when no results have been returned eg. when no rules exist |
| **AsAt** | **DateTimeOffset** | Required | Legacy AsAt time for backwards compatibility |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRunInfo(
    runId: "...",  // required — The unique identifier of a compliance run
    instigatedAt: DateTimeOffset.Now,  // required — The time the compliance run was launched (e.g. button pressed). Currently it is also both the as at and effective at time in whichthe rule set and portfolio data (including any pending trades if the run is pretrade) is taken for the caluation, although it may be possible to run compliance for historical effective at and as at dates in the future.
    completedAt: DateTimeOffset.Now,  // required — The time the compliance run calculation was completed
    schedule: "...",  // required — Whether the compliance run was pre or post trade
    allRulesPassed: true,  // required — True if all rules passed, for all the portfolios they were assigned to
    hasResults: true,  // required — False when no results have been returned eg. when no rules exist
    asAt: DateTimeOffset.Now  // required — Legacy AsAt time for backwards compatibility
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRunInfo>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

