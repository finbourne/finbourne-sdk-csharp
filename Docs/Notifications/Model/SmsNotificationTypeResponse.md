# Finbourne.Sdk.Notifications.Model.SmsNotificationTypeResponse

Holds readonly information about an SMS notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of delivery mechanism for this notification |
| **Body** | **string** | Optional | The body of the SMS |
| **Recipients** | **List&lt;string&gt;** | Optional | The phone numbers to which the SMS will be sent to (E.164 format) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new SmsNotificationTypeResponse(
    type: "...",  // optional — The type of delivery mechanism for this notification
    body: "...",  // optional — The body of the SMS
    recipients:   // optional — The phone numbers to which the SMS will be sent to (E.164 format)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SmsNotificationTypeResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

