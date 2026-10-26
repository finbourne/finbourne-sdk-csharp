# Finbourne.Sdk.Lusid.Model.BucketSetClassSeed

One share class's seeded bucket values.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShareClassShortCode** | **string** | Required | The short code of the seeded share class. |
| **Buckets** | [List&lt;BucketSeedValue&gt;](BucketSeedValue.md) | Required | The seeded buckets of the share class. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetClassSeed(
    shareClassShortCode: "...",  // required — The short code of the seeded share class.
    buckets: new List<BucketSeedValue>()  // required — The seeded buckets of the share class.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetClassSeed>(json);
```

- [BucketSeedValue](BucketSeedValue.md) — used in `Buckets`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

