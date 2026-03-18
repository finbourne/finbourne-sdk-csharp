# Finbourne.Sdk.Lusid.Model.AddBusinessDaysToDateResponse

The date that is the requested number of business days after the given start date
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **DateTimeOffset** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AddBusinessDaysToDateResponse(
    value: DateTimeOffset.Now  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddBusinessDaysToDateResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

