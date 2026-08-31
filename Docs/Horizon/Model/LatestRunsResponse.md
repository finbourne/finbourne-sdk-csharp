# Finbourne.Sdk.Horizon.Model.LatestRunsResponse

record containing the 24-hour run summary grouped by external status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Total** | **int** | Required | *No description available.* |
| **StatusCounts** | [List&lt;RunStatusCount&gt;](RunStatusCount.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LatestRunsResponse(
    total: 0,  // required
    statusCounts: new List<RunStatusCount>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LatestRunsResponse>(json);
```

- [RunStatusCount](RunStatusCount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

