# Finbourne.Sdk.Notifications.Model.EmailNotificationType

The information required to create or update an Email notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of delivery mechanism for this notification |
| **Subject** | **string** | Required | The subject of the email |
| **PlainTextBody** | **string** | Required | The plain text body of the email |
| **HtmlBody** | **string** | Optional | The HTML body of the email (if any) |
| **EmailAddressTo** | **List&lt;string&gt;** | Required | &#39;To&#39; recipients of the email |
| **EmailAddressCc** | **List&lt;string&gt;** | Optional | &#39;Cc&#39; recipients of the email |
| **EmailAddressBcc** | **List&lt;string&gt;** | Optional | &#39;Bcc&#39; recipients of the email |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new EmailNotificationType(
    type: "...",  // required — The type of delivery mechanism for this notification
    subject: "...",  // required — The subject of the email
    plainTextBody: "...",  // required — The plain text body of the email
    htmlBody: "...",  // optional — The HTML body of the email (if any)
    emailAddressTo: ,  // required — &#39;To&#39; recipients of the email
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
var instance = JsonConvert.DeserializeObject<EmailNotificationType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

