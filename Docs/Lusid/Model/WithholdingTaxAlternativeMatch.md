# Finbourne.Sdk.Lusid.Model.WithholdingTaxAlternativeMatch

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IfValues** | **Dictionary&lt;string, string&gt;** | Required | The values of the unresolved dimensions that choose this row, one or more. |
| **MatchedRuleId** | **string** | Required | The identifier booking would stamp for the row that these values choose. |
| **StopAtSourceRate** | **decimal** | Required | The rate that this row would withhold at source. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxAlternativeMatch(
    ifValues: ,  // required — The values of the unresolved dimensions that choose this row, one or more.
    matchedRuleId: "...",  // required — The identifier booking would stamp for the row that these values choose.
    stopAtSourceRate: 0.0d  // required — The rate that this row would withhold at source.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxAlternativeMatch>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

