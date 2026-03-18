# Finbourne.Sdk.Workflow.Model.SpecifiedTime

A specified time in the day
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Hours** | **int** | Required | Hours |
| **Minutes** | **int** | Required | Minutes |
| **Type** | **string** | Required | The type of Time of Day |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new SpecifiedTime(
    hours: 0,  // required — Hours
    minutes: 0,  // required — Minutes
    type: "..."  // required — The type of Time of Day
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SpecifiedTime>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

