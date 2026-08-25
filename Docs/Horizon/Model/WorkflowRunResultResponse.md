# Finbourne.Sdk.Horizon.Model.WorkflowRunResultResponse

A single declared field and the value this run published for it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | *No description available.* |
| **Type** | **string** | Required | One of the Workflow field types: String, Decimal, DateTime, Boolean, LusidUserId. |
| **Value** | **string** | Optional | The published value, or null when the run published nothing for this field. |
| **DisplayName** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new WorkflowRunResultResponse(
    name: "...",  // required
    type: "...",  // required — One of the Workflow field types: String, Decimal, DateTime, Boolean, LusidUserId.
    value: "...",  // optional — The published value, or null when the run published nothing for this field.
    displayName: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowRunResultResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

