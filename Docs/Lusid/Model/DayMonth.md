# Finbourne.Sdk.Lusid.Model.DayMonth

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Day** | **int** | Required | Day part of Day, Month for Year End date specification. |
| **Month** | **int** | Required | Month part of Day, Month for Year End date specification. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DayMonth(
    day: 0,  // required — Day part of Day, Month for Year End date specification.
    month: 0  // required — Month part of Day, Month for Year End date specification.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DayMonth>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

