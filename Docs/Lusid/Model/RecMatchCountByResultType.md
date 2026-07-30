# Finbourne.Sdk.Lusid.Model.RecMatchCountByResultType

Match result counts broken down by result type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Match** | **int** | Required | The number of Match results. |
| **Cross** | **int** | Required | The number of Cross results. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecMatchCountByResultType(
    match: 0,  // required — The number of Match results.
    cross: 0  // required — The number of Cross results.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecMatchCountByResultType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

