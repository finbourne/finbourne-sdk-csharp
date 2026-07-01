# Finbourne.Sdk.Lusid.Model.ResolveTenorsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | *No description available.* |
| **SpotDate** | **DateTimeOffset** | Required | *No description available.* |
| **EomRuleApplied** | **bool** | Required | *No description available.* |
| **Dates** | **Dictionary&lt;string, DateTimeOffset&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResolveTenorsResponse(
    startDate: DateTimeOffset.Now,  // required
    spotDate: DateTimeOffset.Now,  // required
    eomRuleApplied: true,  // required
    dates:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResolveTenorsResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

