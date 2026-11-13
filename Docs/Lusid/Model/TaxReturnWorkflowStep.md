# Finbourne.Sdk.Lusid.Model.TaxReturnWorkflowStep

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Optional | The workflow status of the return. Available values: Draft, Prepared, Reviewed, SignedOff, Final. Available values: Draft, Prepared, Reviewed, SignedOff, Final. |
| **AsAt** | **DateTimeOffset** | Optional | The time the workflow step was recorded. |
| **Reason** | **string** | Optional | The reason given when the return was advanced or sent back. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReturnWorkflowStep(
    status: "...",  // optional — The workflow status of the return. Available values: Draft, Prepared, Reviewed, SignedOff, Final. Available values: Draft, Prepared, Reviewed, SignedOff, Final.
    asAt: DateTimeOffset.Now,  // optional — The time the workflow step was recorded.
    reason: "..."  // optional — The reason given when the return was advanced or sent back.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReturnWorkflowStep>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

