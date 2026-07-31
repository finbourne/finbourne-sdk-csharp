# Finbourne.Sdk.Insights.Model.RelativeOffset

A relative offset back from \"now\", e.g. `{ Amount = 2, Unit = Hours }` meaning two hours before now.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **int** | Required | The number of units to go back from now. Must be at least 1. |
| **Unit** | **string** | Required | The unit of the offset. One of the Finbourne.Insights.WebApi.Dtos.Querying.RelativeTimeUnit values. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new RelativeOffset(
    amount: 0,  // required — The number of units to go back from now. Must be at least 1.
    unit: "..."  // required — The unit of the offset. One of the Finbourne.Insights.WebApi.Dtos.Querying.RelativeTimeUnit values.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelativeOffset>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

