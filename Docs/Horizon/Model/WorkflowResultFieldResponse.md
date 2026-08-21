# Finbourne.Sdk.Horizon.Model.WorkflowResultFieldResponse

A single declared field.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | *No description available.* |
| **Type** | **string** | Required | One of the Workflow field types: String, Decimal, DateTime, Boolean, LusidUserId. |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new WorkflowResultFieldResponse(
    name: "...",  // required
    type: "...",  // required — One of the Workflow field types: String, Decimal, DateTime, Boolean, LusidUserId.
    displayName: "...",  // optional
    description: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowResultFieldResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

