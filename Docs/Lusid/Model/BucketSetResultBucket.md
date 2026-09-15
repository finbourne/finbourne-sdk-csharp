# Finbourne.Sdk.Lusid.Model.BucketSetResultBucket

One bucket's values within a bucket set node: the movement in the period plus the cumulative values before  and after it (CumulativeValue = Value + PreviousCumulativeValue), and - on share class nodes - the breakdown  of the movement by the source that contributed it and the same values restated per unit in issue.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketId** | **string** | Required | The identifier of the bucket. |
| **BucketType** | **string** | Required | The type of the bucket (for example Dealing or PnL). |
| **Value** | **decimal** | Required | The movement in the bucket over the valuation point&#39;s period. |
| **PreviousCumulativeValue** | **decimal** | Required | The cumulative value of the bucket up to the start of the period. |
| **CumulativeValue** | **decimal** | Required | The cumulative value of the bucket up to the end of the period (Value + PreviousCumulativeValue). |
| **SourceBreakdown** | **Dictionary&lt;string, decimal&gt;** | Optional | The bucket&#39;s movement broken down by the source that contributed it, which always sums to Value. Set on share class nodes only. The keys are &#39;classSpecific&#39; for amounts booked directly to the share class, &#39;nonClassSpecific&#39; for fund-level amounts apportioned to it, and an allocation group&#39;s code for amounts allocated to that group and apportioned to the share class. Sources contributing nothing to the bucket are omitted. |
| **PerUnitValue** | **decimal?** | Optional | The bucket&#39;s movement over the period per unit in issue (Value divided by UnitsInIssue), in the fund currency, rounded to the share class&#39;s PricePrecision. Reported only where both the share class and the bucket are unitised and there are units in issue to divide by. |
| **UnitsInIssue** | **decimal?** | Optional | The share class&#39;s units in issue at the end of the period. Reported only where both the share class and the bucket are unitised. |
| **PreviousCumulativePerUnitValue** | **decimal?** | Optional | The bucket&#39;s cumulative value at the start of the period, per unit in issue at that point - so it reads as it did at the previous valuation point rather than being restated at this period&#39;s unit count. |
| **CumulativePerUnitValue** | **decimal?** | Optional | The bucket&#39;s cumulative value at the end of the period per unit in issue (CumulativeValue divided by UnitsInIssue). Reported only where both the share class and the bucket are unitised and there are units in issue to divide by. |
| **DisplayName** | **string** | Optional | The display name of the bucket, as configured on the fund configuration. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetResultBucket(
    bucketId: "...",  // required — The identifier of the bucket.
    bucketType: "...",  // required — The type of the bucket (for example Dealing or PnL).
    value: 0.0d,  // required — The movement in the bucket over the valuation point&#39;s period.
    previousCumulativeValue: 0.0d,  // required — The cumulative value of the bucket up to the start of the period.
    cumulativeValue: 0.0d,  // required — The cumulative value of the bucket up to the end of the period (Value + PreviousCumulativeValue).
    sourceBreakdown: ,  // optional — The bucket&#39;s movement broken down by the source that contributed it, which always sums to Value. Set on share class nodes only. The keys are &#39;classSpecific&#39; for amounts booked directly to the share class, &#39;nonClassSpecific&#39; for fund-level amounts apportioned to it, and an allocation group&#39;s code for amounts allocated to that group and apportioned to the share class. Sources contributing nothing to the bucket are omitted.
    perUnitValue: 0.0d,  // optional — The bucket&#39;s movement over the period per unit in issue (Value divided by UnitsInIssue), in the fund currency, rounded to the share class&#39;s PricePrecision. Reported only where both the share class and the bucket are unitised and there are units in issue to divide by.
    unitsInIssue: 0.0d,  // optional — The share class&#39;s units in issue at the end of the period. Reported only where both the share class and the bucket are unitised.
    previousCumulativePerUnitValue: 0.0d,  // optional — The bucket&#39;s cumulative value at the start of the period, per unit in issue at that point - so it reads as it did at the previous valuation point rather than being restated at this period&#39;s unit count.
    cumulativePerUnitValue: 0.0d,  // optional — The bucket&#39;s cumulative value at the end of the period per unit in issue (CumulativeValue divided by UnitsInIssue). Reported only where both the share class and the bucket are unitised and there are units in issue to divide by.
    displayName: "..."  // optional — The display name of the bucket, as configured on the fund configuration.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetResultBucket>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

