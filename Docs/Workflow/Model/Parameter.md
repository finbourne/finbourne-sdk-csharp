# Finbourne.Sdk.Workflow.Model.Parameter

Defines a Worker Parameter
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of this Parameter |
| **Name** | **string** | Required | Name |
| **DisplayName** | **string** | Optional | DisplayName |
| **Description** | **string** | Optional | Description |
| **Required** | **bool** | Required | Required or not |
| **DefaultValue** | **string** | Optional | DefaultValue |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new Parameter(
    type: "...",  // required — The type of this Parameter
    name: "...",  // required — Name
    displayName: "...",  // optional — DisplayName
    description: "...",  // optional — Description
    required: true,  // required — Required or not
    defaultValue: "..."  // optional — DefaultValue
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Parameter>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

