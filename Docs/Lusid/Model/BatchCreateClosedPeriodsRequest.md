# Finbourne.Sdk.Lusid.Model.BatchCreateClosedPeriodsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ClosedPeriods** | [List&lt;CreateClosedPeriodRequest&gt;](CreateClosedPeriodRequest.md) | Required | The ordered set of Closed Periods to create. Each Closed Period&#39;s EffectiveStart is derived from the previous Closed Period&#39;s EffectiveEnd (or the current chain tail for the first item), so EffectiveEnd must be strictly increasing across the batch. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchCreateClosedPeriodsRequest(
    closedPeriods: new List<CreateClosedPeriodRequest>()  // required — The ordered set of Closed Periods to create. Each Closed Period&#39;s EffectiveStart is derived from the previous Closed Period&#39;s EffectiveEnd (or the current chain tail for the first item), so EffectiveEnd must be strictly increasing across the batch.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchCreateClosedPeriodsRequest>(json);
```


## Related Models

- [CreateClosedPeriodRequest](CreateClosedPeriodRequest.md) — used in `ClosedPeriods`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

