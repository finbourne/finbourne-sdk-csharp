# Finbourne.Sdk.Lusid.Model.SettlementProblem

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SettlementInstructionId** | **string** | Required | The id of the problematic settlement instruction. Combined with the portfolio id this uniquely identifies a settlement instruction |
| **Category** | **string** | Required | The category this instruction belongs to |
| **Status** | **string** | Required | The status of the settlement instruction. Possible values are &#39;Invalid&#39; or &#39;Rejected&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementProblem(
    settlementInstructionId: "...",  // required — The id of the problematic settlement instruction. Combined with the portfolio id this uniquely identifies a settlement instruction
    category: "...",  // required — The category this instruction belongs to
    status: "..."  // required — The status of the settlement instruction. Possible values are &#39;Invalid&#39; or &#39;Rejected&#39;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementProblem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

