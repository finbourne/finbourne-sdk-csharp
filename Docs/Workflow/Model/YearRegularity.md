# Finbourne.Sdk.Workflow.Model.YearRegularity

Year Regularity
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Dates** | [List&lt;DayOfYear&gt;](DayOfYear.md) | Required | The dates in the year |
| **Type** | **string** | Required | The type of Date Regularity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new YearRegularity(
    dates: new List<DayOfYear>(),  // required — The dates in the year
    type: "..."  // required — The type of Date Regularity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<YearRegularity>(json);
```


## Related Models

- [DayOfYear](DayOfYear.md) — used in `Dates`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

