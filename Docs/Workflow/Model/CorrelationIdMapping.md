# Finbourne.Sdk.Workflow.Model.CorrelationIdMapping

How an Event Launcher fills one correlation ID of the root task from the event that arrived.              A mapped correlation ID joins the fixed correlation IDs of the Launcher
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MapFrom** | **string** | Required | The path into the event the correlation ID is taken from, for example body.fileId |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CorrelationIdMapping(
    mapFrom: "..."  // required — The path into the event the correlation ID is taken from, for example body.fileId
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CorrelationIdMapping>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

