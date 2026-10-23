# Finbourne.Sdk.Lusid.Model.MarginRun

A margin run: the valuation of the collateral agreements for a business date, planned as shards that report  their progress, and the margin calls and lines it has published so far.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The URI of this margin run. |
| **Id** | **string** | Required | The identifier of the run: the effective date and the asAt it was valued at. Filterable. |
| **EffectiveAt** | **DateTimeOffset** | Required | The business date the run values collateral agreements for. Filterable. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime the run reads agreements, portfolios and market data at. Filterable. |
| **Status** | **string** | Required | The status of the run. One of Pending, Running, Completed or CompletedWithIssues. Filterable. |
| **Agreements** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The collateral agreements the run covers. |
| **CallCount** | **int** | Required | The number of margin calls the run has published so far. |
| **LineCount** | **int** | Required | The number of margin lines the run has published so far. |
| **ShardCount** | **int** | Required | The number of valuation shards the run was planned as. |
| **CompletedShards** | **int** | Required | The number of shards that have completed. |
| **FailedShards** | **int** | Required | The number of shards that failed to value. |
| **Issues** | [List&lt;MarginRunIssue&gt;](MarginRunIssue.md) | Required | Agreements the run could not value or roll up into a call, or the caller may not calculate margin for, with the reason. |
| **Shards** | [List&lt;MarginRunShard&gt;](MarginRunShard.md) | Required | The valuation shards the run is planned as, with their progress. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginRun(
    href: "...",  // optional — The URI of this margin run.
    id: "...",  // required — The identifier of the run: the effective date and the asAt it was valued at. Filterable.
    effectiveAt: DateTimeOffset.Now,  // required — The business date the run values collateral agreements for. Filterable.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime the run reads agreements, portfolios and market data at. Filterable.
    status: "...",  // required — The status of the run. One of Pending, Running, Completed or CompletedWithIssues. Filterable.
    agreements: new List<ResourceId>(),  // required — The collateral agreements the run covers.
    callCount: 0,  // required — The number of margin calls the run has published so far.
    lineCount: 0,  // required — The number of margin lines the run has published so far.
    shardCount: 0,  // required — The number of valuation shards the run was planned as.
    completedShards: 0,  // required — The number of shards that have completed.
    failedShards: 0,  // required — The number of shards that failed to value.
    issues: new List<MarginRunIssue>(),  // required — Agreements the run could not value or roll up into a call, or the caller may not calculate margin for, with the reason.
    shards: new List<MarginRunShard>()  // required — The valuation shards the run is planned as, with their progress.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginRun>(json);
```

- [ResourceId](ResourceId.md) — used in `Agreements`
- [MarginRunIssue](MarginRunIssue.md) — used in `Issues`
- [MarginRunShard](MarginRunShard.md) — used in `Shards`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

