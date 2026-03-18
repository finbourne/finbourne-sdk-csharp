# Finbourne.Sdk.Workflow.Model.CalendarReference

Reference to a Calendar in LUSID
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope of the Calendar |
| **Code** | **string** | Required | The code of the Calendar |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CalendarReference(
    scope: "...",  // required — The scope of the Calendar
    code: "..."  // required — The code of the Calendar
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CalendarReference>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

