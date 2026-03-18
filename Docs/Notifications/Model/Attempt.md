# Finbourne.Sdk.Notifications.Model.Attempt

Details of an attempt of delivery.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AttemptNumber** | **int** | Required | The attempt number of the delivery. |
| **AttemptTime** | **DateTimeOffset** | Required | The time that the delivery was attempted. |
| **Status** | [AttemptStatus](AttemptStatus.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new Attempt(
    attemptNumber: 0,  // required — The attempt number of the delivery.
    attemptTime: DateTimeOffset.Now,  // required — The time that the delivery was attempted.
    status: new AttemptStatus(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Attempt>(json);
```

- [AttemptStatus](AttemptStatus.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

