# Finbourne.Sdk.Luminesce.Model.DateParameters

Collection of date parameters used in dashboards
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DateFrom** | **DateTimeOffset?** | Optional | Parameter to determine the lower bound in a date range |
| **DateTo** | **DateTimeOffset?** | Optional | Parameter to determine the upper bound in a date range |
| **EffectiveAt** | **DateTimeOffset?** | Optional | EffectiveAt of the dashboard |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | EffectiveFrom of the dashboard |
| **AsAt** | **DateTimeOffset** | Required | AsAt of the dashboard |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new DateParameters(
    dateFrom: DateTimeOffset.Now,  // optional — Parameter to determine the lower bound in a date range
    dateTo: DateTimeOffset.Now,  // optional — Parameter to determine the upper bound in a date range
    effectiveAt: DateTimeOffset.Now,  // optional — EffectiveAt of the dashboard
    effectiveFrom: DateTimeOffset.Now,  // optional — EffectiveFrom of the dashboard
    asAt: DateTimeOffset.Now  // required — AsAt of the dashboard
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DateParameters>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

