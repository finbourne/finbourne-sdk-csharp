# Finbourne.Sdk.Workflow.Model.SpecificMonthRegularity

Specific Month Regularity
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Frequency** | **int** | Required | The frequency of the Specific Month Regularity. For example, a value of 2 indicates every 2 months |
| **DaysOfMonth** | **List&lt;int&gt;** | Required | Days of the month. For example, to specify the 1st and 15th of every month, set DaysOfMonth to [1, 15] |
| **Type** | **string** | Required | The type of Date Regularity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new SpecificMonthRegularity(
    frequency: 0,  // required — The frequency of the Specific Month Regularity. For example, a value of 2 indicates every 2 months
    daysOfMonth: ,  // required — Days of the month. For example, to specify the 1st and 15th of every month, set DaysOfMonth to [1, 15]
    type: "..."  // required — The type of Date Regularity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SpecificMonthRegularity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

