# Finbourne.Sdk.Luminesce.Model.ViewParameter

Parameters of view
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | Name of the provider |
| **DataType** | **DataType** | Required | *No description available.* |
| **Value** | **string** | Required | Value of the provider |
| **IsTableDataMandatory** | **bool** | Optional | Should this be selected? False would imply it is only being filtered on. Ignored when Aggregations are present |
| **Description** | **string** | Optional | Description of the parameter |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ViewParameter(
    name: "...",  // required — Name of the provider
    dataType: ,  // required
    value: "...",  // required — Value of the provider
    isTableDataMandatory: true,  // optional — Should this be selected? False would imply it is only being filtered on. Ignored when Aggregations are present
    description: "..."  // optional — Description of the parameter
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ViewParameter>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

