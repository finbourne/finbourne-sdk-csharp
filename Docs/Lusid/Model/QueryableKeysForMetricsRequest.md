# Finbourne.Sdk.Lusid.Model.QueryableKeysForMetricsRequest

Specification of the metrics whose queryable key definitions are being requested.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Metrics** | **List&lt;string&gt;** | Required | The address keys of the metrics to describe, given exactly as they would be supplied as the key of  a valuation request&#39;s metrics, for example &#39;Valuation/PV&#39; or &#39;Holding/Properties[Holding/MyScope/Rating]&#39;. |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective time to describe the metrics at, for definitions and entitlements that vary  along the effective timeline. Optional; defaults to the current time. |
| **AsAt** | **DateTimeOffset?** | Optional | The as-at time to describe the metrics at. Optional; defaults to the latest. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryableKeysForMetricsRequest(
    metrics: ,  // required — The address keys of the metrics to describe, given exactly as they would be supplied as the key of  a valuation request&#39;s metrics, for example &#39;Valuation/PV&#39; or &#39;Holding/Properties[Holding/MyScope/Rating]&#39;.
    recipeId: new ResourceId(...),  // optional
    effectiveAt: DateTimeOffset.Now,  // optional — The effective time to describe the metrics at, for definitions and entitlements that vary  along the effective timeline. Optional; defaults to the current time.
    asAt: DateTimeOffset.Now  // optional — The as-at time to describe the metrics at. Optional; defaults to the latest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryableKeysForMetricsRequest>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

