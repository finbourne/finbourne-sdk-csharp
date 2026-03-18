# Finbourne.Sdk.Workflow.Model.ParameterValue

Defines a Parameter Value
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | Name |
| **Value** | **Object** | Optional | Value which can be a String, Boolean, Decimal or DateTime (ISO 8601) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ParameterValue(
    name: "...",  // required — Name
    value:   // optional — Value which can be a String, Boolean, Decimal or DateTime (ISO 8601)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ParameterValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

