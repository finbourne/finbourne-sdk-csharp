# Finbourne.Sdk.Horizon.Model.InstanceResponse

record containing details of a single instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **Guid** | Required | *No description available.* |
| **Name** | **string** | Required | *No description available.* |
| **Enabled** | **bool** | Required | *No description available.* |
| **Portfolios** | [List&lt;TpfPortfolio&gt;](TpfPortfolio.md) | Required | *No description available.* |
| **Schedule** | **string** | Optional | *No description available.* |
| **ScheduleTimezone** | **string** | Optional | *No description available.* |
| **LastRunAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **LastRunStatus** | **string** | Optional | *No description available.* |
| **LatestRunsIn24Hours** | **string** | Optional | *No description available.* |
| **Destinations** | [List&lt;InstanceDestinations&gt;](InstanceDestinations.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new InstanceResponse(
    id: "...",  // required
    name: "...",  // required
    enabled: true,  // required
    portfolios: new List<TpfPortfolio>(),  // required
    schedule: "...",  // optional
    scheduleTimezone: "...",  // optional
    lastRunAt: DateTimeOffset.Now,  // optional
    lastRunStatus: "...",  // optional
    latestRunsIn24Hours: "...",  // optional
    destinations: new List<InstanceDestinations>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstanceResponse>(json);
```

- [TpfPortfolio](TpfPortfolio.md)
- [InstanceDestinations](InstanceDestinations.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

