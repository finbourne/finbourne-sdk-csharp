# Finbourne.Sdk.Luminesce.Model.BackgroundQueryCancelResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HadData** | **bool** | Optional | *No description available.* |
| **PreviousStatus** | **TaskStatus** | Optional | *No description available.* |
| **PreviousState** | **BackgroundQueryState** | Optional | *No description available.* |
| **Progress** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new BackgroundQueryCancelResponse(
    hadData: true,  // optional
    previousStatus: ,  // optional
    previousState: ,  // optional
    progress: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BackgroundQueryCancelResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

