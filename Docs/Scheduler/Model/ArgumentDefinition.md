# Finbourne.Sdk.Scheduler.Model.ArgumentDefinition

Job argument definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DataType** | **string** | Required | Data type of the argument |
| **Required** | **bool** | Optional | Optionality of the argument |
| **Description** | **string** | Required | Argument description |
| **Order** | **int** | Required | The order of the argument |
| **Constraints** | **string** | Optional | Constrains of the argument value |
| **PassedAs** | **string** | Required | Specifies how this argument should be passed in Allowed values are: CommandLine or EnvironmentVariable  Defaults to: CommandLine |
| **DefaultValue** | **string** | Optional | Specify a default value for this argument if no value is provided The value needs to be convertible to the associated data type |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new ArgumentDefinition(
    dataType: "...",  // required — Data type of the argument
    required: true,  // optional — Optionality of the argument
    description: "...",  // required — Argument description
    order: 0,  // required — The order of the argument
    constraints: "...",  // optional — Constrains of the argument value
    passedAs: "...",  // required — Specifies how this argument should be passed in Allowed values are: CommandLine or EnvironmentVariable  Defaults to: CommandLine
    defaultValue: "..."  // optional — Specify a default value for this argument if no value is provided The value needs to be convertible to the associated data type
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ArgumentDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

