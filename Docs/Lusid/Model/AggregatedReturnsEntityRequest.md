# Finbourne.Sdk.Lusid.Model.AggregatedReturnsEntityRequest

The request body for the aggregated-returns (TWR) endpoint: the entity to calculate returns for, the  Returns entity that configures the calculation, the effective window, the metrics to calculate and the  period grid granularity. Supports a single `Portfolio` entity, the period `Return` metric and  a `Daily` grid.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Entity** | [AggregatedReturnsEntityId](AggregatedReturnsEntityId.md) | Required | *No description available.* |
| **ReturnsScope** | **string** | Required | *No description available.* |
| **ReturnsCode** | **string** | Required | *No description available.* |
| **Metrics** | [List&lt;ReturnsMetric&gt;](ReturnsMetric.md) | Required | *No description available.* |
| **Period** | **string** | Optional | Available values: Daily, Monthly. |
| **FromEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | *No description available.* |
| **ToEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | *No description available.* |
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregatedReturnsEntityRequest(
    entity: new AggregatedReturnsEntityId(...),  // required
    returnsScope: "...",  // required
    returnsCode: "...",  // required
    metrics: new List<ReturnsMetric>(),  // required
    period: "...",  // optional — Available values: Daily, Monthly.
    fromEffectiveAt: new DateTimeOrCutLabel(...),  // optional
    toEffectiveAt: new DateTimeOrCutLabel(...),  // optional
    asAt: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregatedReturnsEntityRequest>(json);
```


## Related Models

- [AggregatedReturnsEntityId](AggregatedReturnsEntityId.md)
- [ReturnsMetric](ReturnsMetric.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

