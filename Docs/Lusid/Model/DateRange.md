# Finbourne.Sdk.Lusid.Model.DateRange

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FromDate** | **DateTimeOffset** | Required | *No description available.* |
| **UntilDate** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DateRange(
    fromDate: DateTimeOffset.Now,  // required
    untilDate: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DateRange>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

