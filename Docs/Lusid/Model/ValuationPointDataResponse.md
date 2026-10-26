# Finbourne.Sdk.Lusid.Model.ValuationPointDataResponse

The Valuation Point Data Response for the Fund and specified date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Type** | **string** | Required | The Type of the associated Diary Entry (&#39;PeriodBoundary&#39;,&#39;ValuationPoint&#39;,&#39;Other&#39; or &#39;Adhoc&#39; when a diary entry wasn&#39;t used). Available values: PeriodBoundary, ValuationPoint, Other, Adhoc. |
| **Status** | **string** | Required | The status of a Diary Entry of Type &#39;ValuationPoint&#39;. Defaults to &#39;Estimate&#39; when upserting a diary entry, moves to &#39;Candidate&#39; or &#39;Final&#39; when a ValuationPoint is accepted, and &#39;Final&#39; when it is finalised.  The status of a Diary Entry becomes &#39;Unofficial&#39; when a diary entry wasn&#39;t used. Available values: Undefined, Estimate, Final, Candidate, Rejected, Unofficial. |
| **FundDetails** | [FundDetails](FundDetails.md) | Required | *No description available.* |
| **FundValuationPointData** | [FundValuationPointData](FundValuationPointData.md) | Required | *No description available.* |
| **ShareClassData** | [List&lt;ShareClassData&gt;](ShareClassData.md) | Required | The data for all share classes in fund. Share classes are identified by their short codes. |
| **ValuationPointCode** | **string** | Optional | The code of the valuation point. |
| **PreviousValuationPointCode** | **string** | Optional | The code of the previous valuation point. |
| **ApportionmentResults** | [List&lt;ApportionmentBreakdown&gt;](ApportionmentBreakdown.md) | Optional | The apportionment results for the valuation point: one fund-level entry plus one entry per allocation group. |
| **BucketSetResults** | [List&lt;BucketSetResult&gt;](BucketSetResult.md) | Optional | The bucket set results for the valuation point: for each bucket set, the per-node (fund and share class) buckets and NAV. |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **IsBackfilled** | **bool** | Optional | Set to True if the Valuation Point has backfilled bucket set results, False otherwise. |
| **ApplyClearDown** | **bool** | Optional | Set to True if the Valuation Point applies a clear down, False otherwise. The Valuation Point shows its bucket values before the clear down, and the next Valuation Point opens from the balances after it. |
| **Diagnostics** | [List&lt;ValuationPointDiagnostic&gt;](ValuationPointDiagnostic.md) | Optional | Findings made while striking the valuation point that did not stop it but should be looked at, such as a fund structure holder whose declared sharing percentage in a member has drifted from the share its contributions make of that member&#39;s capital. Absent when there are none. |
| **BucketSetSeeds** | [List&lt;BucketSetSeed&gt;](BucketSetSeed.md) | Optional | The bucket set seeds set on the Valuation Point, when the request resolved to the Valuation Point itself. Null when it has none. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPointDataResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    type: "...",  // required — The Type of the associated Diary Entry (&#39;PeriodBoundary&#39;,&#39;ValuationPoint&#39;,&#39;Other&#39; or &#39;Adhoc&#39; when a diary entry wasn&#39;t used). Available values: PeriodBoundary, ValuationPoint, Other, Adhoc.
    status: "...",  // required — The status of a Diary Entry of Type &#39;ValuationPoint&#39;. Defaults to &#39;Estimate&#39; when upserting a diary entry, moves to &#39;Candidate&#39; or &#39;Final&#39; when a ValuationPoint is accepted, and &#39;Final&#39; when it is finalised.  The status of a Diary Entry becomes &#39;Unofficial&#39; when a diary entry wasn&#39;t used. Available values: Undefined, Estimate, Final, Candidate, Rejected, Unofficial.
    fundDetails: new FundDetails(...),  // required
    fundValuationPointData: new FundValuationPointData(...),  // required
    shareClassData: new List<ShareClassData>(),  // required — The data for all share classes in fund. Share classes are identified by their short codes.
    valuationPointCode: "...",  // optional — The code of the valuation point.
    previousValuationPointCode: "...",  // optional — The code of the previous valuation point.
    apportionmentResults: new List<ApportionmentBreakdown>(),  // optional — The apportionment results for the valuation point: one fund-level entry plus one entry per allocation group.
    bucketSetResults: new List<BucketSetResult>(),  // optional — The bucket set results for the valuation point: for each bucket set, the per-node (fund and share class) buckets and NAV.
    stagedModifications: new StagedModificationsInfo(...),  // optional
    isBackfilled: true,  // optional — Set to True if the Valuation Point has backfilled bucket set results, False otherwise.
    applyClearDown: true,  // optional — Set to True if the Valuation Point applies a clear down, False otherwise. The Valuation Point shows its bucket values before the clear down, and the next Valuation Point opens from the balances after it.
    diagnostics: new List<ValuationPointDiagnostic>(),  // optional — Findings made while striking the valuation point that did not stop it but should be looked at, such as a fund structure holder whose declared sharing percentage in a member has drifted from the share its contributions make of that member&#39;s capital. Absent when there are none.
    bucketSetSeeds: new List<BucketSetSeed>(),  // optional — The bucket set seeds set on the Valuation Point, when the request resolved to the Valuation Point itself. Null when it has none.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPointDataResponse>(json);
```

- [FundDetails](FundDetails.md)
- [FundValuationPointData](FundValuationPointData.md)
- [ShareClassData](ShareClassData.md) — used in `ShareClassData`
- [ApportionmentBreakdown](ApportionmentBreakdown.md) — used in `ApportionmentResults`
- [BucketSetResult](BucketSetResult.md) — used in `BucketSetResults`
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [ValuationPointDiagnostic](ValuationPointDiagnostic.md) — used in `Diagnostics`
- [BucketSetSeed](BucketSetSeed.md) — used in `BucketSetSeeds`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

