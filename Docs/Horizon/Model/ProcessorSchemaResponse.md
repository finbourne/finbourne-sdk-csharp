# Finbourne.Sdk.Horizon.Model.ProcessorSchemaResponse

DTO ProcessorSchemaResponse fields with JObject
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ProcessorName** | **string** | Required | *No description available.* |
| **VarVersion** | **string** | Required | *No description available.* |
| **ConfigurationSchema** | **Object** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ProcessorSchemaResponse(
    processorName: "...",  // required
    varVersion: "...",  // required
    configurationSchema:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessorSchemaResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

