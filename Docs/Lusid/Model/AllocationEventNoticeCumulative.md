# Finbourne.Sdk.Lusid.Model.AllocationEventNoticeCumulative

Cumulative balances to date for a partner on a notice.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Contributions** | **decimal** | Required | Cumulative contributions after the event. |
| **Distributions** | **decimal** | Required | Cumulative distributions after the event. |
| **Recallable** | **decimal** | Required | Cumulative recallable distributions after the event. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventNoticeCumulative(
    contributions: 0.0d,  // required — Cumulative contributions after the event.
    distributions: 0.0d,  // required — Cumulative distributions after the event.
    recallable: 0.0d  // required — Cumulative recallable distributions after the event.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventNoticeCumulative>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

