# Finbourne.Sdk.Lusid.Model.NoticeConvention

Defines the notice period by which a cancellation election must be made ahead of the  cancel effective date, else the option lapses.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Calendars** | **List&lt;string&gt;** | Optional | Holiday calendar code(s) used to resolve business days, required when the day type is Business. |
| **DayType** | **string** | Required | Indicates whether the notice days are counted using business days or calendar days.                Supported string (enumeration) values are: [Business, Calendar]. Available values: Business, Calendar. |
| **NoticeDays** | **int** | Optional | The number of days prior to the cancel effective date by which the election must be made.                Defaults to 2 if not set. Default: `2` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NoticeConvention(
    calendars: ,  // optional — Holiday calendar code(s) used to resolve business days, required when the day type is Business.
    dayType: "...",  // required — Indicates whether the notice days are counted using business days or calendar days.                Supported string (enumeration) values are: [Business, Calendar]. Available values: Business, Calendar.
    noticeDays: 0  // optional — The number of days prior to the cancel effective date by which the election must be made.                Defaults to 2 if not set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NoticeConvention>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

