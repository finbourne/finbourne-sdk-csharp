# Finbourne.Sdk.Insights.Model.TraceLog

Holds metadata for a trace.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TraceId** | **string** | Required | The identifier of the trace. |
| **CreatedAt** | **DateTimeOffset** | Required | The datetime at which the trace was created. |
| **UserId** | **string** | Required | The id of the user who created the trace. |
| **Description** | **string** | Optional | The description of the trace. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new TraceLog(
    traceId: "...",  // required — The identifier of the trace.
    createdAt: DateTimeOffset.Now,  // required — The datetime at which the trace was created.
    userId: "...",  // required — The id of the user who created the trace.
    description: "...",  // optional — The description of the trace.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TraceLog>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

