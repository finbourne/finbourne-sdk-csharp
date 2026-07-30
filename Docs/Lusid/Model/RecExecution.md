# Finbourne.Sdk.Lusid.Model.RecExecution

The execution outcome for a run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Outcome** | **string** | Required | The execution outcome. Available values: Succeeded, Failed. |
| **ErrorDetail** | **string** | Optional | Detail of the execution failure. Populated when outcome is Failed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecExecution(
    outcome: "...",  // required — The execution outcome. Available values: Succeeded, Failed.
    errorDetail: "..."  // optional — Detail of the execution failure. Populated when outcome is Failed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecExecution>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

