# Finbourne.Sdk.Notifications.Model.EmailNotificationTypeResponse

Holds readonly information about an Email notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of delivery mechanism for this notification |
| **Subject** | **string** | Optional | The subject of the email |
| **PlainTextBody** | **string** | Optional | The plain text body of the email |
| **HtmlBody** | **string** | Optional | The HTML body of the email (if any) |
| **EmailAddressTo** | **List&lt;string&gt;** | Optional | &#39;To&#39; recipients of the email |
| **EmailAddressCc** | **List&lt;string&gt;** | Optional | &#39;Cc&#39; recipients of the email |
| **EmailAddressBcc** | **List&lt;string&gt;** | Optional | &#39;Bcc&#39; recipients of the email |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new EmailNotificationTypeResponse(
    type: "...",  // optional — The type of delivery mechanism for this notification
    subject: "...",  // optional — The subject of the email
    plainTextBody: "...",  // optional — The plain text body of the email
    htmlBody: "...",  // optional — The HTML body of the email (if any)
    emailAddressTo: ,  // optional — &#39;To&#39; recipients of the email
    emailAddressCc: ,  // optional — &#39;Cc&#39; recipients of the email
    emailAddressBcc:   // optional — &#39;Bcc&#39; recipients of the email
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EmailNotificationTypeResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

