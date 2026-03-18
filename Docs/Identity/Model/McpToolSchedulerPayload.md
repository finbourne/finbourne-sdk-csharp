# Finbourne.Sdk.Identity.Model.McpToolSchedulerPayload

Payload data for a Scheduler job MCP tool
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **JobScope** | **string** | Required | The scope of the scheduler job to run |
| **JobCode** | **string** | Required | The code of the scheduler job to run |
| **Arguments** | **Dictionary&lt;string, string&gt;** | Optional | Arguments to pass to the scheduler job (key-value pairs) |
| **RunAs** | **string** | Optional | Optional service user identifier to run the job as (if not the current user) |
| **Notifications** | [List&lt;McpToolSchedulerNotification&gt;](McpToolSchedulerNotification.md) | Optional | Optional additional notifications for the job |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new McpToolSchedulerPayload(
    jobScope: "...",  // required — The scope of the scheduler job to run
    jobCode: "...",  // required — The code of the scheduler job to run
    arguments: ,  // optional — Arguments to pass to the scheduler job (key-value pairs)
    runAs: "...",  // optional — Optional service user identifier to run the job as (if not the current user)
    notifications: new List<McpToolSchedulerNotification>()  // optional — Optional additional notifications for the job
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<McpToolSchedulerPayload>(json);
```

- [McpToolSchedulerNotification](McpToolSchedulerNotification.md) — used in `Notifications`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

