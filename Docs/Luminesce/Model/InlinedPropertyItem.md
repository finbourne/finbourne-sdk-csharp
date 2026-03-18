# Finbourne.Sdk.Luminesce.Model.InlinedPropertyItem

Information about a inlined property so that decorated properties can be inlined into luminesce
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | Key of the property |
| **Name** | **string** | Optional | Name of the property |
| **IsMain** | **bool** | Optional | Is Main indicator for the property |
| **Description** | **string** | Optional | Description of the property |
| **DataType** | **string** | Optional | Data type of the property |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new InlinedPropertyItem(
    key: "...",  // required — Key of the property
    name: "...",  // optional — Name of the property
    isMain: true,  // optional — Is Main indicator for the property
    description: "...",  // optional — Description of the property
    dataType: "..."  // optional — Data type of the property
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InlinedPropertyItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

