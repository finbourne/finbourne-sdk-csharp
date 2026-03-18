# Finbourne.Sdk.Lusid.Model.Premium

A class containing information for a given premium payment.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **decimal** | Required | Premium amount. |
| **Currency** | **string** | Required | Premium currency. |
| **Date** | **DateTimeOffset** | Required | Date when premium paid. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Premium(
    amount: 0.0d,  // required — Premium amount.
    currency: "...",  // required — Premium currency.
    date: DateTimeOffset.Now  // required — Date when premium paid.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Premium>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

