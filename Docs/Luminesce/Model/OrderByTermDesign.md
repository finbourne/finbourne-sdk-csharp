# Finbourne.Sdk.Luminesce.Model.OrderByTermDesign

A single clause within an Order BY
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Field** | **string** | Required | Name of the field to order by |
| **Direction** | **OrderByDirection** | Optional | *No description available.* |
| **TableAlias** | **string** | Optional | Table Alias of the field to order by |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new OrderByTermDesign(
    field: "...",  // required — Name of the field to order by
    direction: ,  // optional
    tableAlias: "..."  // optional — Table Alias of the field to order by
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderByTermDesign>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

