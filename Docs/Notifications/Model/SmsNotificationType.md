# Finbourne.Sdk.Notifications.Model.SmsNotificationType

The information required to create or update an SMS notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of delivery mechanism for this notification |
| **Body** | **string** | Required | The body of the SMS |
| **Recipients** | **List&lt;string&gt;** | Required | The phone numbers to which the SMS will be sent to (E.164 format) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new SmsNotificationType(
    type: "...",  // required — The type of delivery mechanism for this notification
    body: "...",  // required — The body of the SMS
    recipients:   // required — The phone numbers to which the SMS will be sent to (E.164 format)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SmsNotificationType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

