# Finbourne.Sdk.Horizon.Model.IIntegrationLogResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LogId** | **long** | Required | *No description available.* *(read-only)* |
| **RunId** | **Guid?** | Optional | *No description available.* *(read-only)* |
| **ParentLogId** | **long?** | Optional | *No description available.* *(read-only)* |
| **LogType** | **string** | Required | *No description available.* *(read-only)* |
| **FirstActivity** | **DateTimeOffset?** | Optional | *No description available.* *(read-only)* |
| **LastActivity** | **DateTimeOffset?** | Optional | *No description available.* *(read-only)* |
| **Status** | **string** | Optional | *No description available.* *(read-only)* |
| **SourceRecord** | [IntegrationLogRecord](IntegrationLogRecord.md) | Optional | *No description available.* |
| **TargetRecord** | [IntegrationLogTargetRecord](IntegrationLogTargetRecord.md) | Optional | *No description available.* |
| **Activities** | [List&lt;IntegrationLogActivity&gt;](IntegrationLogActivity.md) | Required | *No description available.* *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IIntegrationLogResponse(
    logId: 0L,  // required
    runId: "...",  // optional
    parentLogId: 0L,  // optional
    logType: "...",  // required
    firstActivity: DateTimeOffset.Now,  // optional
    lastActivity: DateTimeOffset.Now,  // optional
    status: "...",  // optional
    sourceRecord: new IntegrationLogRecord(...),  // optional
    targetRecord: new IntegrationLogTargetRecord(...),  // optional
    activities: new List<IntegrationLogActivity>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IIntegrationLogResponse>(json);
```

- [IntegrationLogRecord](IntegrationLogRecord.md)
- [IntegrationLogTargetRecord](IntegrationLogTargetRecord.md)
- [IntegrationLogActivity](IntegrationLogActivity.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

