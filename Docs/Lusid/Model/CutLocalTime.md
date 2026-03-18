# Finbourne.Sdk.Lusid.Model.CutLocalTime

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Hours** | **int** | Optional | *No description available.* |
| **Minutes** | **int** | Optional | *No description available.* |
| **Seconds** | **decimal** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CutLocalTime(
    hours: 0,  // optional
    minutes: 0,  // optional
    seconds: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CutLocalTime>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

