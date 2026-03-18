# Finbourne.Sdk.Insights.Model.Bucket

A single histogram bucket.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartTime** | **DateTimeOffset** | Optional | The bucket&#39;s start time as a DateTimeOffset. |
| **ItemCount** | **long** | Optional | The number of items in the bucket. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new Bucket(
    startTime: DateTimeOffset.Now,  // optional — The bucket&#39;s start time as a DateTimeOffset.
    itemCount: 0L  // optional — The number of items in the bucket.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Bucket>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

