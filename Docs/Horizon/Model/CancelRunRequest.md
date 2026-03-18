# Finbourne.Sdk.Horizon.Model.CancelRunRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunIds** | **List&lt;string&gt;** | Required | *No description available.* |
| **Message** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new CancelRunRequest(
    runIds: ,  // required
    message: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CancelRunRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

