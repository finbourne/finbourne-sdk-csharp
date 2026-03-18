# Finbourne.Sdk.Lusid.Model.BucketingSchedule

A schedule for dates
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Tenor** | **string** | Optional | Rolling tenor |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketingSchedule(
    tenor: "..."  // optional — Rolling tenor
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketingSchedule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

