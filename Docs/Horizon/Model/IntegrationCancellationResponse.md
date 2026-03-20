# Finbourne.Sdk.Horizon.Model.IntegrationCancellationResponse

No content is returned when an instance is cancelled.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Response** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationCancellationResponse(
    response:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationCancellationResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

