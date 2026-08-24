# Finbourne.Sdk.Lusid.Model.TransactionTypeDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope in which the TransactionType was resolved. If the portfolio has a TransactionTypeScope, this will have been used. Otherwise the default scope will have been used. |
| **Source** | **string** | Required | The source in which the TransactionType was resolved. |
| **Type** | **string** | Required | The resolved TransactionType. More information on TransactionType resolution can be found at https://support.lusid.com/docs/how-does-lusid-resolve-transactions-to-transaction-types |
| **MovementConditionMatches** | [List&lt;MovementConditionMatch&gt;](MovementConditionMatch.md) | Optional | One entry for each movement on the resolved TransactionType, in the order the movements are configured, recording whether that movement&#39;s condition was satisfied by this transaction. Empty for transaction versions that generate no movements, such as cancelled and amended versions. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionTypeDetails(
    scope: "...",  // required — The scope in which the TransactionType was resolved. If the portfolio has a TransactionTypeScope, this will have been used. Otherwise the default scope will have been used.
    source: "...",  // required — The source in which the TransactionType was resolved.
    type: "...",  // required — The resolved TransactionType. More information on TransactionType resolution can be found at https://support.lusid.com/docs/how-does-lusid-resolve-transactions-to-transaction-types
    movementConditionMatches: new List<MovementConditionMatch>()  // optional — One entry for each movement on the resolved TransactionType, in the order the movements are configured, recording whether that movement&#39;s condition was satisfied by this transaction. Empty for transaction versions that generate no movements, such as cancelled and amended versions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionTypeDetails>(json);
```

- [MovementConditionMatch](MovementConditionMatch.md) — used in `MovementConditionMatches`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

