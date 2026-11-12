# Finbourne.Sdk.Lusid.Model.MarginRunOptimisation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | How far the pass got. One of Pending, Completed, Skipped or Failed. |
| **RecommendationCount** | **int** | Required | How many recommendations the pass made. |
| **Detail** | **string** | Optional | What the pass left out and why, or why it failed. Null when nothing was left out. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginRunOptimisation(
    status: "...",  // required — How far the pass got. One of Pending, Completed, Skipped or Failed.
    recommendationCount: 0,  // required — How many recommendations the pass made.
    detail: "..."  // optional — What the pass left out and why, or why it failed. Null when nothing was left out.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginRunOptimisation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

