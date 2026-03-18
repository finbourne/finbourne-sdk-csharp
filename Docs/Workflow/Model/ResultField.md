# Finbourne.Sdk.Workflow.Model.ResultField

Defines a Worker Result Field
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | Name |
| **Type** | **string** | Required | The type of this Parameter |
| **DisplayName** | **string** | Optional | DisplayName |
| **Description** | **string** | Optional | Description |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ResultField(
    name: "...",  // required — Name
    type: "...",  // required — The type of this Parameter
    displayName: "...",  // optional — DisplayName
    description: "..."  // optional — Description
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

