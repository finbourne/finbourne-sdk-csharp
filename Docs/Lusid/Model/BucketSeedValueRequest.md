# Finbourne.Sdk.Lusid.Model.BucketSeedValueRequest

One bucket's cumulative value to seed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketId** | **string** | Required | The identifier of the seeded bucket. |
| **AbsoluteValue** | **decimal** | Required | The bucket&#39;s cumulative value at the valuation point, in the fund currency. It is trusted input: nothing reconciles it to the share class NAV. |
| **PerUnitValue** | **decimal?** | Optional | The bucket&#39;s cumulative value per unit in issue. It is stored rounded to the share class&#39;s price precision. When omitted on a unitised bucket it is the absolute value over the share class&#39;s units in issue at the valuation point. Must be omitted on a bucket that is not unitised. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSeedValueRequest(
    bucketId: "...",  // required — The identifier of the seeded bucket.
    absoluteValue: 0.0d,  // required — The bucket&#39;s cumulative value at the valuation point, in the fund currency. It is trusted input: nothing reconciles it to the share class NAV.
    perUnitValue: 0.0d  // optional — The bucket&#39;s cumulative value per unit in issue. It is stored rounded to the share class&#39;s price precision. When omitted on a unitised bucket it is the absolute value over the share class&#39;s units in issue at the valuation point. Must be omitted on a bucket that is not unitised.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSeedValueRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

