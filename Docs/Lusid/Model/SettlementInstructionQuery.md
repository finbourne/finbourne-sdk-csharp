# Finbourne.Sdk.Lusid.Model.SettlementInstructionQuery

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **StartDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | *No description available.* |
| **EndDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | *No description available.* |
| **Limit** | **int?** | Optional | *No description available.* |
| **Page** | **string** | Optional | *No description available.* |
| **Filter** | **string** | Optional | *No description available.* |
| **SettlementInstructionPropertyKeys** | **List&lt;string&gt;** | Optional | *No description available.* |
| **TransactionPropertyKeys** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementInstructionQuery(
    asAt: DateTimeOffset.Now,  // optional
    startDate: new DateTimeOrCutLabel(...),  // optional
    endDate: new DateTimeOrCutLabel(...),  // optional
    limit: 0,  // optional
    page: "...",  // optional
    filter: "...",  // optional
    settlementInstructionPropertyKeys: ,  // optional
    transactionPropertyKeys:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementInstructionQuery>(json);
```

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

