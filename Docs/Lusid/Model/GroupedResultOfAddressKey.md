# Finbourne.Sdk.Lusid.Model.GroupedResultOfAddressKey

Holder class for a group of results. It consists of a list of columns and values for that column.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Columns** | **List&lt;string&gt;** | Optional | The columns, or keys, for a particular group of results |
| **Values** | [List&lt;ResultValue&gt;](ResultValue.md) | Optional | The values for the list of results |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupedResultOfAddressKey(
    columns: ,  // optional — The columns, or keys, for a particular group of results
    values: new List<ResultValue>()  // optional — The values for the list of results
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupedResultOfAddressKey>(json);
```

- [ResultValue](ResultValue.md) — used in `Values`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

