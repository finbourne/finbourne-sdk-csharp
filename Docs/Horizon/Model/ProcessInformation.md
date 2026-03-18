# Finbourne.Sdk.Horizon.Model.ProcessInformation

Required information for each process
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Domain** | **string** | Required | *No description available.* |
| **ProcessName** | **string** | Required | *No description available.* |
| **RunId** | **string** | Required | *No description available.* |
| **StartTime** | **DateTimeOffset** | Required | *No description available.* |
| **DataAction** | **string** | Required | *No description available.* |
| **SchemaVersion** | **string** | Optional | *No description available.* |
| **UserId** | **string** | Required | *No description available.* |
| **ProcessSummary** | [ProcessSummary](ProcessSummary.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ProcessInformation(
    domain: "...",  // required
    processName: "...",  // required
    runId: "...",  // required
    startTime: DateTimeOffset.Now,  // required
    dataAction: "...",  // required
    schemaVersion: "...",  // optional
    userId: "...",  // required
    processSummary: new ProcessSummary(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessInformation>(json);
```

- [ProcessSummary](ProcessSummary.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

