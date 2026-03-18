# Finbourne.Sdk.Lusid.Model.WeekendMask

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Days** | [List&lt;DayOfWeek&gt;](DayOfWeek.md) | Required | *No description available.* |
| **VarTimeZone** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WeekendMask(
    days: new List<DayOfWeek>(),  // required
    varTimeZone: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WeekendMask>(json);
```


## Related Models

- [DayOfWeek](DayOfWeek.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

