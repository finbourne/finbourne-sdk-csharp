# Finbourne.Sdk.Lusid.Model.BucketCashFlowBucket

One tenor bucket for one portfolio, payment currency and set of sub-holding keys: its opening balance, closing balance and the  cash flows that make up its activity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketId** | **string** | Optional | Identifies the bucket: a 32 character lowercase hexadecimal hash of its period (start and end), payment currency, portfolio and sub-holding keys. It is stable, the same bucket has the same id in every response, and it is opaque: compare it, do not take it apart. |
| **BucketStart** | **DateTimeOffset** | Optional | The start of the period the bucket covers. |
| **BucketEnd** | **DateTimeOffset** | Optional | The end of the period the bucket covers. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Currency** | **string** | Optional | The payment currency of the bucket. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding keys the bucket is for, limited to those the caller may read. |
| **Open** | [BucketAmounts](BucketAmounts.md) | Optional | *No description available.* |
| **ActivityTotal** | [BucketAmounts](BucketAmounts.md) | Optional | *No description available.* |
| **Activity** | [List&lt;CashFlowDetail&gt;](CashFlowDetail.md) | Optional | The cash flows in the bucket, with the attributes a cash flow has in Values. |
| **Close** | [BucketAmounts](BucketAmounts.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketCashFlowBucket(
    bucketId: "...",  // optional — Identifies the bucket: a 32 character lowercase hexadecimal hash of its period (start and end), payment currency, portfolio and sub-holding keys. It is stable, the same bucket has the same id in every response, and it is opaque: compare it, do not take it apart.
    bucketStart: DateTimeOffset.Now,  // optional — The start of the period the bucket covers.
    bucketEnd: DateTimeOffset.Now,  // optional — The end of the period the bucket covers.
    portfolioId: new ResourceId(...),  // optional
    currency: "...",  // optional — The payment currency of the bucket.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding keys the bucket is for, limited to those the caller may read.
    open: new BucketAmounts(...),  // optional
    activityTotal: new BucketAmounts(...),  // optional
    activity: new List<CashFlowDetail>(),  // optional — The cash flows in the bucket, with the attributes a cash flow has in Values.
    close: new BucketAmounts(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketCashFlowBucket>(json);
```

- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [BucketAmounts](BucketAmounts.md)
- [BucketAmounts](BucketAmounts.md)
- [CashFlowDetail](CashFlowDetail.md) — used in `Activity`
- [BucketAmounts](BucketAmounts.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

