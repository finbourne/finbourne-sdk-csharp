# Finbourne.Sdk.Lusid.Model.SettlementInstructionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SettlementInstructionId** | **string** | Required | *No description available.* |
| **TransactionId** | **string** | Required | *No description available.* |
| **SettlementCategory** | **string** | Required | *No description available.* |
| **InstructionType** | **string** | Optional | *No description available.* |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **ContractualSettlementDate** | **DateTimeOffset?** | Optional | *No description available.* |
| **ActualSettlementDate** | **DateTimeOffset** | Required | *No description available.* |
| **Units** | **decimal** | Required | *No description available.* |
| **SubHoldingKeyOverrides** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | *No description available.* |
| **CustodianAccountOverride** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstructionToPortfolioRate** | **decimal?** | Optional | *No description available.* |
| **SettlementInLieu** | [SettlementInLieu](SettlementInLieu.md) | Optional | *No description available.* |
| **Properties** | [List&lt;PerpetualProperty&gt;](PerpetualProperty.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementInstructionRequest(
    settlementInstructionId: "...",  // required
    transactionId: "...",  // required
    settlementCategory: "...",  // required
    instructionType: "...",  // optional
    instrumentIdentifiers: ,  // required
    contractualSettlementDate: DateTimeOffset.Now,  // optional
    actualSettlementDate: DateTimeOffset.Now,  // required
    units: 0.0d,  // required
    subHoldingKeyOverrides: new PerpetualProperty(...),  // optional
    custodianAccountOverride: new ResourceId(...),  // optional
    instructionToPortfolioRate: 0.0d,  // optional
    settlementInLieu: new SettlementInLieu(...),  // optional
    properties: new List<PerpetualProperty>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementInstructionRequest>(json);
```

- [PerpetualProperty](PerpetualProperty.md)
- [ResourceId](ResourceId.md)
- [SettlementInLieu](SettlementInLieu.md)
- [PerpetualProperty](PerpetualProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

