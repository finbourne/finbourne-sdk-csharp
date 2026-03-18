# Finbourne.Sdk.Notifications.Model.ManualEventRequest

The information required to trigger a manual event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Body** | [ManualEventBody](ManualEventBody.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new ManualEventRequest(
    body: new ManualEventBody(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManualEventRequest>(json);
```


## Related Models

- [ManualEventBody](ManualEventBody.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

