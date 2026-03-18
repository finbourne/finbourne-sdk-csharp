# Finbourne.Sdk.Luminesce.Model.TableMeta

Representation of the table metadata
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TableId** | **string** | Required | A unique identifier for the table |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new TableMeta(
    tableId: "..."  // required — A unique identifier for the table
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TableMeta>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

