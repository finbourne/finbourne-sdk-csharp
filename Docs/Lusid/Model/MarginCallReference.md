# Finbourne.Sdk.Lusid.Model.MarginCallReference

A pointer to a margin call in another run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Required | The run the referenced call belongs to. |
| **CallId** | **string** | Required | The business key of the referenced call. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginCallReference(
    runId: "...",  // required — The run the referenced call belongs to.
    callId: "..."  // required — The business key of the referenced call.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginCallReference>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

