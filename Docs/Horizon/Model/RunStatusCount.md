# Finbourne.Sdk.Horizon.Model.RunStatusCount

record containing the count of runs for a given status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | *No description available.* |
| **Count** | **int** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new RunStatusCount(
    status: "...",  // required
    count: 0  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunStatusCount>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

