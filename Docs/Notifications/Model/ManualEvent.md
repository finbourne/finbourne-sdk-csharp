# Finbourne.Sdk.Notifications.Model.ManualEvent

Details of a manually triggered event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Header** | [ManualEventHeader](ManualEventHeader.md) | Required | *No description available.* |
| **Body** | [ManualEventBody](ManualEventBody.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new ManualEvent(
    header: new ManualEventHeader(...),  // required
    body: new ManualEventBody(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManualEvent>(json);
```


## Related Models

- [ManualEventHeader](ManualEventHeader.md)
- [ManualEventBody](ManualEventBody.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

