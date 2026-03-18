# Finbourne.Sdk.Lusid.Model.OrderBreachHistory

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **OrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RunId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **BreachesByRule** | **Dictionary&lt;string, List&lt;OrderRuleBreach&gt;&gt;** | Optional | Compliance rule breaches associations with the order and run. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime at which the order breach was created in LUSID. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderBreachHistory(
    id: new ResourceId(...),  // required
    orderId: new ResourceId(...),  // required
    runId: new ResourceId(...),  // required
    breachesByRule: ,  // optional — Compliance rule breaches associations with the order and run.
    asAt: DateTimeOffset.Now  // required — The asAt datetime at which the order breach was created in LUSID.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderBreachHistory>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

