# Finbourne.Sdk.Lusid.Model.SettlementSchedule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TradeId** | **string** | Optional | *No description available.* |
| **SettlementDate** | **DateTimeOffset** | Optional | *No description available.* |
| **Units** | **decimal** | Optional | *No description available.* |
| **BondInterest** | **decimal** | Optional | *No description available.* |
| **MovementName** | **string** | Optional | *No description available.* |
| **MovementType** | **string** | Optional | *No description available.* |
| **UnsettledUnits** | **decimal** | Optional | *No description available.* |
| **OverdueUnits** | **decimal** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementSchedule(
    tradeId: "...",  // optional
    settlementDate: DateTimeOffset.Now,  // optional
    units: 0.0d,  // optional
    bondInterest: 0.0d,  // optional
    movementName: "...",  // optional
    movementType: "...",  // optional
    unsettledUnits: 0.0d,  // optional
    overdueUnits: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementSchedule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

