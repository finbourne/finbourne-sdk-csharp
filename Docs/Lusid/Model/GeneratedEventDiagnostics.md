# Finbourne.Sdk.Lusid.Model.GeneratedEventDiagnostics

Represents a set of diagnostics per generatedEvent, where applicable.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentEventId** | **string** | Required | *No description available.* |
| **Type** | **string** | Required | *No description available.* |
| **Detail** | **string** | Required | *No description available.* |
| **ErrorDetails** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GeneratedEventDiagnostics(
    instrumentEventId: "...",  // required
    type: "...",  // required
    detail: "...",  // required
    errorDetails:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GeneratedEventDiagnostics>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

