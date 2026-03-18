# Finbourne.Sdk.Lusid.Model.RunCheckRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LusidEntityDataset** | [LusidEntityDataset](LusidEntityDataset.md) | Optional | *No description available.* |
| **LimitIndividualBreachesPerRule** | **int** | Optional | The maximum number of individual breaches to return per rule. Defaults to 100 if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RunCheckRequest(
    lusidEntityDataset: new LusidEntityDataset(...),  // optional
    limitIndividualBreachesPerRule: 0  // optional — The maximum number of individual breaches to return per rule. Defaults to 100 if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunCheckRequest>(json);
```


## Related Models

- [LusidEntityDataset](LusidEntityDataset.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

