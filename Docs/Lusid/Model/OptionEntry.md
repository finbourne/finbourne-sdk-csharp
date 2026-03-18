# Finbourne.Sdk.Lusid.Model.OptionEntry

Strike price against par and associated date for a bond call.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Strike** | **decimal** | Required | The strike on this date |
| **Date** | **DateTimeOffset** | Required | The date at which the option can be actioned at this strike |
| **EndDate** | **DateTimeOffset?** | Optional | If American exercise, this is the end of the exercise period.  Optional field. Defaults to the Date field if not set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OptionEntry(
    strike: 0.0d,  // required — The strike on this date
    date: DateTimeOffset.Now,  // required — The date at which the option can be actioned at this strike
    endDate: DateTimeOffset.Now  // optional — If American exercise, this is the end of the exercise period.  Optional field. Defaults to the Date field if not set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OptionEntry>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

