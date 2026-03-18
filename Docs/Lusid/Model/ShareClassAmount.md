# Finbourne.Sdk.Lusid.Model.ShareClassAmount

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundCurrencyAmount** | **decimal** | Optional | The value of the amount in the fund currency. |
| **ShareClassCurrencyAmount** | **decimal** | Optional | The value of the amount in the share class currency. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClassAmount(
    fundCurrencyAmount: 0.0d,  // optional — The value of the amount in the fund currency.
    shareClassCurrencyAmount: 0.0d  // optional — The value of the amount in the share class currency.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ShareClassAmount>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

