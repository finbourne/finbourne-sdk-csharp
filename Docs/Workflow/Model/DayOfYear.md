# Finbourne.Sdk.Workflow.Model.DayOfYear

A day in the year
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Month** | **int** | Required | Month in the year |
| **Day** | **int** | Required | Day in the month |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new DayOfYear(
    month: 0,  // required — Month in the year
    day: 0  // required — Day in the month
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DayOfYear>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

