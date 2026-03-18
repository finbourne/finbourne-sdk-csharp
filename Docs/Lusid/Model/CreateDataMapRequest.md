# Finbourne.Sdk.Lusid.Model.CreateDataMapRequest

Request to create a new data map
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [DataMapKey](DataMapKey.md) | Required | *No description available.* |
| **Data** | [DataMapping](DataMapping.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateDataMapRequest(
    id: new DataMapKey(...),  // required
    data: new DataMapping(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateDataMapRequest>(json);
```


## Related Models

- [DataMapKey](DataMapKey.md)
- [DataMapping](DataMapping.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

