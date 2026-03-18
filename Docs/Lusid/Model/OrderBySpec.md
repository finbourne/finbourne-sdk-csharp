# Finbourne.Sdk.Lusid.Model.OrderBySpec

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key that uniquely identifies a queryable address in Lusid. |
| **SortOrder** | **string** | Required | The available values are: Ascending, Descending |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderBySpec(
    key: "...",  // required — The key that uniquely identifies a queryable address in Lusid.
    sortOrder: "..."  // required — The available values are: Ascending, Descending
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderBySpec>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

