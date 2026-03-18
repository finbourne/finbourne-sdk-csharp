# Finbourne.Sdk.Lusid.Model.RolloverConstituent

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ContractDetails** | [ContractDetails](ContractDetails.md) | Required | *No description available.* |
| **BalanceChange** | **decimal** | Required | Balance of the new contract holding. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RolloverConstituent(
    contractDetails: new ContractDetails(...),  // required
    balanceChange: 0.0d  // required — Balance of the new contract holding.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RolloverConstituent>(json);
```


## Related Models

- [ContractDetails](ContractDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

