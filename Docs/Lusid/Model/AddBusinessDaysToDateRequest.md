# Finbourne.Sdk.Lusid.Model.AddBusinessDaysToDateRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BusinessDayOffset** | **int** | Required | *No description available.* |
| **HolidayCodes** | **List&lt;string&gt;** | Required | *No description available.* |
| **StartDate** | **DateTimeOffset** | Optional | *No description available.* |
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AddBusinessDaysToDateRequest(
    businessDayOffset: 0,  // required
    holidayCodes: ,  // required
    startDate: DateTimeOffset.Now,  // optional
    asAt: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddBusinessDaysToDateRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

