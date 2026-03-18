# Finbourne.Sdk.Workflow.Model.HealthCheck

Configuration for a Worker that performs a GET against a given Url.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of worker |
| **Url** | **string** | Required | The URL to check, eg: https://www.google.com/ |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new HealthCheck(
    type: "...",  // required — The type of worker
    url: "..."  // required — The URL to check, eg: https://www.google.com/
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HealthCheck>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

