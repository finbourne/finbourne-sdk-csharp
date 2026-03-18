# Finbourne.Sdk.Lusid.Model.IsBusinessDayResponse

Whether or not a DateTimeOffset is a business DateTime
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RequestedDateTime** | **DateTimeOffset** | Required | *No description available.* |
| **IsBusinessDay** | **bool** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IsBusinessDayResponse(
    requestedDateTime: DateTimeOffset.Now,  // required
    isBusinessDay: true  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IsBusinessDayResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

