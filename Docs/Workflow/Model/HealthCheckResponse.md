# Finbourne.Sdk.Workflow.Model.HealthCheckResponse

Readonly configuration for a Worker that performs a GET against a given Url.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of worker |
| **Url** | **string** | Optional | The URL to check, eg: https://www.google.com/ |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new HealthCheckResponse(
    type: "...",  // optional — The type of worker
    url: "..."  // optional — The URL to check, eg: https://www.google.com/
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HealthCheckResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

