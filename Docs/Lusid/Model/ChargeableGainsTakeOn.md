# Finbourne.Sdk.Lusid.Model.ChargeableGainsTakeOn

Carried-forward chargeable-gains balances for a tax-lot taken on under the UK chargeable gains accounting method
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Role** | **string** | Required | Available values: Section104Pool, Holding1982, Holding1965. |
| **Indexation** | **decimal?** | Optional | *No description available.* |
| **IndexedTo** | **DateTimeOffset?** | Optional | *No description available.* |
| **OriginalCost** | **decimal?** | Optional | *No description available.* |
| **MarketValue1982** | **decimal?** | Optional | *No description available.* |
| **RebasingElection** | **bool?** | Optional | *No description available.* |
| **Additions** | [List&lt;ChargeableGainsTakeOnAddition&gt;](ChargeableGainsTakeOnAddition.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ChargeableGainsTakeOn(
    role: "...",  // required — Available values: Section104Pool, Holding1982, Holding1965.
    indexation: 0.0d,  // optional
    indexedTo: DateTimeOffset.Now,  // optional
    originalCost: 0.0d,  // optional
    marketValue1982: 0.0d,  // optional
    rebasingElection: true,  // optional
    additions: new List<ChargeableGainsTakeOnAddition>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ChargeableGainsTakeOn>(json);
```

- [ChargeableGainsTakeOnAddition](ChargeableGainsTakeOnAddition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

