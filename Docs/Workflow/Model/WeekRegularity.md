# Finbourne.Sdk.Workflow.Model.WeekRegularity

Week Regularity
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Frequency** | **int** | Required | The frequency of the Week Regularity. For example, a value of 2 indicates every 2 weeks |
| **DaysOfWeek** | **List&lt;string&gt;** | Required | Days of the week. One or more of - Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday |
| **Type** | **string** | Required | The type of Date Regularity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new WeekRegularity(
    frequency: 0,  // required — The frequency of the Week Regularity. For example, a value of 2 indicates every 2 weeks
    daysOfWeek: ,  // required — Days of the week. One or more of - Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday
    type: "..."  // required — The type of Date Regularity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WeekRegularity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

