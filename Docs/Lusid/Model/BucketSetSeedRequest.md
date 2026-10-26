# Finbourne.Sdk.Lusid.Model.BucketSetSeedRequest

The closing balances to seed for a bucket set on an estimate valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketSetCode** | **string** | Required | The code of the bucket set on the fund configuration to seed. |
| **ClassSeeds** | [List&lt;BucketSetClassSeedRequest&gt;](BucketSetClassSeedRequest.md) | Required | The bucket set&#39;s closing balances at the valuation point, per share class. They replace everything the bucket set holds up to and including the valuation point. A share class or bucket left out is zero. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetSeedRequest(
    bucketSetCode: "...",  // required — The code of the bucket set on the fund configuration to seed.
    classSeeds: new List<BucketSetClassSeedRequest>()  // required — The bucket set&#39;s closing balances at the valuation point, per share class. They replace everything the bucket set holds up to and including the valuation point. A share class or bucket left out is zero.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetSeedRequest>(json);
```

- [BucketSetClassSeedRequest](BucketSetClassSeedRequest.md) — used in `ClassSeeds`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

