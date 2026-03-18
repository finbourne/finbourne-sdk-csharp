# Finbourne.Sdk.Notifications.Model.AttemptStatus

Status of the delivery attempt.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Result** | **string** | Required | Result of the delivery. |
| **DetailedMessage** | **string** | Optional | The detailed message from attempting to deliver the message. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new AttemptStatus(
    result: "...",  // required — Result of the delivery.
    detailedMessage: "..."  // optional — The detailed message from attempting to deliver the message.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AttemptStatus>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

