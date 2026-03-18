# Finbourne.Sdk.Lusid.Model.CreateCalendarRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CalendarId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **CalendarType** | **string** | Required | *No description available.* |
| **WeekendMask** | [WeekendMask](WeekendMask.md) | Required | *No description available.* |
| **SourceProvider** | **string** | Required | *No description available.* |
| **Properties** | [List&lt;Property&gt;](Property.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateCalendarRequest(
    calendarId: new ResourceId(...),  // required
    calendarType: "...",  // required
    weekendMask: new WeekendMask(...),  // required
    sourceProvider: "...",  // required
    properties: new List<Property>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateCalendarRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [WeekendMask](WeekendMask.md)
- [Property](Property.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

