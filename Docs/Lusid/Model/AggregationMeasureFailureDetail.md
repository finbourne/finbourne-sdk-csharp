# Finbourne.Sdk.Lusid.Model.AggregationMeasureFailureDetail

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | *No description available.* |
| **EffectiveAt** | **DateTimeOffset** | Optional | *No description available.* |
| **Measure** | **string** | Optional | *No description available.* |
| **Reason** | **string** | Optional | *No description available.* |
| **Detail** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregationMeasureFailureDetail(
    id: "...",  // optional
    effectiveAt: DateTimeOffset.Now,  // optional
    measure: "...",  // optional
    reason: "...",  // optional
    detail: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregationMeasureFailureDetail>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

