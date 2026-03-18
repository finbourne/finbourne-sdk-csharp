# Finbourne.Sdk.Insights.Model.TraceEventLog

Holds information about a trace event.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TraceEventId** | **string** | Required | The identifier of the trace event. |
| **TraceId** | **string** | Required | The identifier of the parent trace. |
| **CreatedAt** | **DateTimeOffset** | Required | The datetime at which the trace event was created. |
| **EventType** | **string** | Required | The type of the trace event. |
| **Origin** | **string** | Required | Whether the event originated from the AI or the user |
| **Content** | **string** | Required | The content of the trace event. |
| **AgentScope** | **string** | Required | The scope of the agent currently being interacted with |
| **AgentCode** | **string** | Required | The code identifier of the agent currently being interacted with |
| **AgentVersion** | **int** | Required | The version of the circuit in which the trace event occurred. |
| **NodeId** | **string** | Required | The ID of the circuit&#39;s node at which the trace event occured. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new TraceEventLog(
    traceEventId: "...",  // required — The identifier of the trace event.
    traceId: "...",  // required — The identifier of the parent trace.
    createdAt: DateTimeOffset.Now,  // required — The datetime at which the trace event was created.
    eventType: "...",  // required — The type of the trace event.
    origin: "...",  // required — Whether the event originated from the AI or the user
    content: "...",  // required — The content of the trace event.
    agentScope: "...",  // required — The scope of the agent currently being interacted with
    agentCode: "...",  // required — The code identifier of the agent currently being interacted with
    agentVersion: 0,  // required — The version of the circuit in which the trace event occurred.
    nodeId: "...",  // required — The ID of the circuit&#39;s node at which the trace event occured.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TraceEventLog>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

