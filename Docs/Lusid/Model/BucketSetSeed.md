# Finbourne.Sdk.Lusid.Model.BucketSetSeed

The closing balances seeded for a bucket set on a valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketSetCode** | **string** | Required | The code of the seeded bucket set on the fund configuration. |
| **ClassSeeds** | [List&lt;BucketSetClassSeed&gt;](BucketSetClassSeed.md) | Required | The bucket set&#39;s seeded closing balances at the valuation point, per share class. They replace everything the bucket set holds up to and including the valuation point. A share class or bucket not listed is zero. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetSeed(
    bucketSetCode: "...",  // required — The code of the seeded bucket set on the fund configuration.
    classSeeds: new List<BucketSetClassSeed>()  // required — The bucket set&#39;s seeded closing balances at the valuation point, per share class. They replace everything the bucket set holds up to and including the valuation point. A share class or bucket not listed is zero.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetSeed>(json);
```

- [BucketSetClassSeed](BucketSetClassSeed.md) — used in `ClassSeeds`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

