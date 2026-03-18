# Finbourne.Sdk.Workflow.Model.DayRegularity

Day Regularity
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Frequency** | **int** | Required | The frequency of the Day Regularity. For example, a value of 2 indicates every 2 days |
| **Type** | **string** | Required | The type of Date Regularity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new DayRegularity(
    frequency: 0,  // required — The frequency of the Day Regularity. For example, a value of 2 indicates every 2 days
    type: "..."  // required — The type of Date Regularity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DayRegularity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

