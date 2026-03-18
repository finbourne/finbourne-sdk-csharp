# Finbourne.Sdk.Lusid.Model.FundAmount

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **decimal** | Optional | The value of the amount in the fund currency. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundAmount(
    value: 0.0d  // optional — The value of the amount in the fund currency.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundAmount>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

