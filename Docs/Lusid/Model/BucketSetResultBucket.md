# Finbourne.Sdk.Lusid.Model.BucketSetResultBucket

One bucket's values within a bucket set node: the movement in the period plus the cumulative values before  and after it (CumulativeValue = Value + PreviousCumulativeValue).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketId** | **string** | Required | The identifier of the bucket. |
| **BucketType** | **string** | Required | The type of the bucket (for example Dealing or PnL). |
| **Value** | **decimal** | Required | The movement in the bucket over the valuation point&#39;s period. |
| **PreviousCumulativeValue** | **decimal** | Required | The cumulative value of the bucket up to the start of the period. |
| **CumulativeValue** | **decimal** | Required | The cumulative value of the bucket up to the end of the period (Value + PreviousCumulativeValue). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetResultBucket(
    bucketId: "...",  // required — The identifier of the bucket.
    bucketType: "...",  // required — The type of the bucket (for example Dealing or PnL).
    value: 0.0d,  // required — The movement in the bucket over the valuation point&#39;s period.
    previousCumulativeValue: 0.0d,  // required — The cumulative value of the bucket up to the start of the period.
    cumulativeValue: 0.0d  // required — The cumulative value of the bucket up to the end of the period (Value + PreviousCumulativeValue).
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

