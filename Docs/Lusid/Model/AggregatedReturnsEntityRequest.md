# Finbourne.Sdk.Lusid.Model.AggregatedReturnsEntityRequest

The request body for the aggregated-returns endpoint: the entity to report returns for, the returns id  under which upserted returns are stored and the Returns entity that configures a calculation, the  effective window, the metrics to report and the period grid granularity. Supports a single  `Portfolio` entity, the period `Return` metric and a `Daily` grid.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Entity** | [AggregatedReturnsEntityId](AggregatedReturnsEntityId.md) | Required | *No description available.* |
| **ReturnsId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Metrics** | [List&lt;ReturnsMetric&gt;](ReturnsMetric.md) | Required | *No description available.* |
| **Period** | **string** | Optional | Available values: Daily, Monthly. |
| **FromEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | *No description available.* |
| **ToEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | *No description available.* |
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **Currency** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregatedReturnsEntityRequest(
    entity: new AggregatedReturnsEntityId(...),  // required
    returnsId: new ResourceId(...),  // required
    metrics: new List<ReturnsMetric>(),  // required
    period: "...",  // optional — Available values: Daily, Monthly.
    fromEffectiveAt: new DateTimeOrCutLabel(...),  // optional
    toEffectiveAt: new DateTimeOrCutLabel(...),  // optional
    asAt: DateTimeOffset.Now,  // optional
    currency: "..."  // optional
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
- [ResourceId](ResourceId.md)
- [ReturnsMetric](ReturnsMetric.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

