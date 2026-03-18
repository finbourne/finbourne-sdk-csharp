# Finbourne.Sdk.Workflow.Model.RelativeMonthRegularity

Relative Month Regularity
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Frequency** | **int** | Required | The frequency of the Relative Month Regularity. For example, a value of 2 indicates every 2 months |
| **DaysOfWeek** | **List&lt;string&gt;** | Required | Days of the week. One or more of - Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday |
| **Index** | **string** | Required | Relative index in the month. One of - First, Second, Third, Fourth, Last. For example, to specify the second Tuesday of every month, set DaysOfWeek to [\&quot;Tuesday\&quot;] and Index to \&quot;Second\&quot; |
| **Type** | **string** | Required | The type of Date Regularity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new RelativeMonthRegularity(
    frequency: 0,  // required — The frequency of the Relative Month Regularity. For example, a value of 2 indicates every 2 months
    daysOfWeek: ,  // required — Days of the week. One or more of - Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday
    index: "...",  // required — Relative index in the month. One of - First, Second, Third, Fourth, Last. For example, to specify the second Tuesday of every month, set DaysOfWeek to [\&quot;Tuesday\&quot;] and Index to \&quot;Second\&quot;
    type: "..."  // required — The type of Date Regularity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelativeMonthRegularity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

