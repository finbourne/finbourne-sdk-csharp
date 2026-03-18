# Finbourne.Sdk.Workflow.Model.DateRegularity

A Date Regularity

## oneOf Type

`DateRegularity` can be one of the following types:

* [DayRegularity](./DayRegularity.md)
* [RelativeMonthRegularity](./RelativeMonthRegularity.md)
* [SpecificMonthRegularity](./SpecificMonthRegularity.md)
* [WeekRegularity](./WeekRegularity.md)
* [YearRegularity](./YearRegularity.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new DayRegularity(...);
var instance = new DateRegularity(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DateRegularity>(json);
```

## Related Models

- [DayRegularity](./DayRegularity.md)
- [RelativeMonthRegularity](./RelativeMonthRegularity.md)
- [SpecificMonthRegularity](./SpecificMonthRegularity.md)
- [WeekRegularity](./WeekRegularity.md)
- [YearRegularity](./YearRegularity.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

