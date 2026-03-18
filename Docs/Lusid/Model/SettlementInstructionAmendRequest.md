# Finbourne.Sdk.Lusid.Model.SettlementInstructionAmendRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SettlementInstructionId** | **string** | Required | *No description available.* |
| **Operation** | **string** | Optional | *No description available.* |
| **Properties** | [List&lt;PerpetualProperty&gt;](PerpetualProperty.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementInstructionAmendRequest(
    settlementInstructionId: "...",  // required
    operation: "...",  // optional
    properties: new List<PerpetualProperty>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementInstructionAmendRequest>(json);
```

- [PerpetualProperty](PerpetualProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

