# Finbourne.Sdk.Lusid.Model.BucketSetClassSeedRequest

One share class's bucket values to seed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShareClassShortCode** | **string** | Required | The short code of the seeded share class. |
| **Buckets** | [List&lt;BucketSeedValueRequest&gt;](BucketSeedValueRequest.md) | Required | The seeded buckets of the share class. Only the bucket set&#39;s flow buckets (dealing, P&amp;L and fees) accumulate, so only they can be seeded. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetClassSeedRequest(
    shareClassShortCode: "...",  // required — The short code of the seeded share class.
    buckets: new List<BucketSeedValueRequest>()  // required — The seeded buckets of the share class. Only the bucket set&#39;s flow buckets (dealing, P&amp;L and fees) accumulate, so only they can be seeded.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetClassSeedRequest>(json);
```

- [BucketSeedValueRequest](BucketSeedValueRequest.md) — used in `Buckets`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

