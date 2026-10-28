# Finbourne.Sdk.Horizon.Model.WorkflowExecuteParameterResponse

A single execute parameter.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | *No description available.* |
| **Type** | **string** | Required | One of the Workflow field types: String, Decimal, DateTime, Boolean. |
| **Required** | **bool** | Required | Whether every run must supply the parameter, whatever its stage. |
| **DisplayName** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Format** | **string** | Optional | The shape a String value must take, e.g. YYYY-MM, when it has one. |
| **AllowedValues** | **List&lt;string&gt;** | Optional | The closed set of accepted values, when there is one. |
| **RequiredForStages** | **List&lt;string&gt;** | Required | The stages for which the parameter is mandatory. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new WorkflowExecuteParameterResponse(
    name: "...",  // required
    type: "...",  // required — One of the Workflow field types: String, Decimal, DateTime, Boolean.
    required: true,  // required — Whether every run must supply the parameter, whatever its stage.
    displayName: "...",  // required
    description: "...",  // required
    format: "...",  // optional — The shape a String value must take, e.g. YYYY-MM, when it has one.
    allowedValues: ,  // optional — The closed set of accepted values, when there is one.
    requiredForStages:   // required — The stages for which the parameter is mandatory.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowExecuteParameterResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

