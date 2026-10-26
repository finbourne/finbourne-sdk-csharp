# Finbourne.Sdk.Lusid.Model.BucketSeedValue

One bucket's seeded cumulative value, as stored.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketId** | **string** | Required | The identifier of the seeded bucket. |
| **AbsoluteValue** | **decimal** | Required | The bucket&#39;s seeded cumulative value at the valuation point, in the fund currency. |
| **PerUnitValue** | **decimal?** | Optional | The per-unit value given with the seed, unrounded. Omitted where none was given, in which case the valuation point reads it off the share class&#39;s units in issue. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSeedValue(
    bucketId: "...",  // required — The identifier of the seeded bucket.
    absoluteValue: 0.0d,  // required — The bucket&#39;s seeded cumulative value at the valuation point, in the fund currency.
    perUnitValue: 0.0d  // optional — The per-unit value given with the seed, unrounded. Omitted where none was given, in which case the valuation point reads it off the share class&#39;s units in issue.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSeedValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

