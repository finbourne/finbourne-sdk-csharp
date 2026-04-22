# Finbourne.Sdk.Horizon.Model.UpdateClientConfigurationDraftRequest

Request to update the value of an existing draft client configuration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | The new JSON value to store. Must be valid JSON. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new UpdateClientConfigurationDraftRequest(
    value: "..."  // required — The new JSON value to store. Must be valid JSON.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateClientConfigurationDraftRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

