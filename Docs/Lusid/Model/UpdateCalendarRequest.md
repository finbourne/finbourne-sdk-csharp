# Finbourne.Sdk.Lusid.Model.UpdateCalendarRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WeekendMask** | [WeekendMask](WeekendMask.md) | Required | *No description available.* |
| **SourceProvider** | **string** | Required | *No description available.* |
| **Properties** | [List&lt;Property&gt;](Property.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateCalendarRequest(
    weekendMask: new WeekendMask(...),  // required
    sourceProvider: "...",  // required
    properties: new List<Property>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateCalendarRequest>(json);
```


## Related Models

- [WeekendMask](WeekendMask.md)
- [Property](Property.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

