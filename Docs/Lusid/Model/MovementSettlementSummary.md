# Finbourne.Sdk.Lusid.Model.MovementSettlementSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | *No description available.* |
| **Type** | **string** | Optional | *No description available.* |
| **LusidInstrumentId** | **string** | Optional | *No description available.* |
| **InstrumentScope** | **string** | Optional | *No description available.* |
| **SettlementMode** | **string** | Optional | *No description available.* |
| **ContractualSettlementDate** | **string** | Optional | *No description available.* |
| **Units** | **decimal** | Optional | *No description available.* |
| **SettledUnits** | **decimal** | Optional | *No description available.* |
| **UnsettledUnits** | **decimal** | Optional | *No description available.* |
| **OverdueUnits** | **decimal** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MovementSettlementSummary(
    name: "...",  // optional
    type: "...",  // optional
    lusidInstrumentId: "...",  // optional
    instrumentScope: "...",  // optional
    settlementMode: "...",  // optional
    contractualSettlementDate: "...",  // optional
    units: 0.0d,  // optional
    settledUnits: 0.0d,  // optional
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
var instance = JsonConvert.DeserializeObject<MovementSettlementSummary>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

