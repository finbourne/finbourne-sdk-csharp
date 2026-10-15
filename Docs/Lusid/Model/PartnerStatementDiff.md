# Finbourne.Sdk.Lusid.Model.PartnerStatementDiff

The differences between two of a partner's statements.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StatementId** | **string** | Required | The identifier of the statement. |
| **AgainstStatementId** | **string** | Required | The identifier of the statement to compare against. |
| **Identical** | **bool** | Required | Whether the two statements carry the same figures. |
| **Differences** | [List&lt;PartnerStatementLineDifference&gt;](PartnerStatementLineDifference.md) | Required | The figures that differ between the two statements. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerStatementDiff(
    statementId: "...",  // required — The identifier of the statement.
    againstStatementId: "...",  // required — The identifier of the statement to compare against.
    identical: true,  // required — Whether the two statements carry the same figures.
    differences: new List<PartnerStatementLineDifference>()  // required — The figures that differ between the two statements.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerStatementDiff>(json);
```

- [PartnerStatementLineDifference](PartnerStatementLineDifference.md) — used in `Differences`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

