# Finbourne.Sdk.Luminesce.Model.ScalarParameter

Describes a scalar parameter as defined in the SQL
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | Name of the scalar parameter |
| **Type** | **DataType** | Required | *No description available.* |
| **Value** | **Object** | Optional | the default value of the parameter |
| **ValueOptions** | **List&lt;Object&gt;** | Optional | Values of the parameter listed as being available for choosing from. |
| **ValueMustBeFromOptions** | **bool** | Optional | Must Value be one of ValueOptions (if any)? |
| **ParameterValueOptionsQuery** | **string** | Optional | SQL that might have been used for generating the options list |
| **ParameterValueOptionsQueryError** | **string** | Optional | Error generated but executing ParameterValueOptionsQuery, if any |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ScalarParameter(
    name: "...",  // required — Name of the scalar parameter
    type: ,  // required
    value: ,  // optional — the default value of the parameter
    valueOptions: ,  // optional — Values of the parameter listed as being available for choosing from.
    valueMustBeFromOptions: true,  // optional — Must Value be one of ValueOptions (if any)?
    parameterValueOptionsQuery: "...",  // optional — SQL that might have been used for generating the options list
    parameterValueOptionsQueryError: "..."  // optional — Error generated but executing ParameterValueOptionsQuery, if any
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScalarParameter>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

