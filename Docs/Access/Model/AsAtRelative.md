# Finbourne.Sdk.Access.Model.AsAtRelative

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **PointInTimeSpecification** | Optional | *No description available.* |
| **Adjustment** | **int** | Optional | *No description available.* |
| **Unit** | **DateUnit** | Optional | *No description available.* |
| **RelativeToDateTime** | **RelativeToDateTime** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new AsAtRelative(
    date: ,  // optional
    adjustment: 0,  // optional
    unit: ,  // optional
    relativeToDateTime:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AsAtRelative>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

