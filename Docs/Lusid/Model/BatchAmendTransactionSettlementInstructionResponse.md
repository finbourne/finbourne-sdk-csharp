# Finbourne.Sdk.Lusid.Model.BatchAmendTransactionSettlementInstructionResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | [Dictionary&lt;string, TransactionSettlementInstruction&gt;](TransactionSettlementInstruction.md) | Optional | The settlement instructions which have been successfully upserted. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The request ids of the settlement instructions which could not be upserted, along with a reason for their failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchAmendTransactionSettlementInstructionResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: new TransactionSettlementInstruction(...),  // optional — The settlement instructions which have been successfully upserted.
    failed: new ErrorDetail(...),  // optional — The request ids of the settlement instructions which could not be upserted, along with a reason for their failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchAmendTransactionSettlementInstructionResponse>(json);
```

- [TransactionSettlementInstruction](TransactionSettlementInstruction.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

