# Finbourne.Sdk.Lusid.Model.TrialBalance

A TrialBalance entity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GeneralLedgerAccountCode** | **string** | Required | The Account code that the trial balance results have been grouped against. |
| **Description** | **string** | Optional | The description of the record. |
| **Levels** | **List&lt;string&gt;** | Required | The levels that have been derived from the specified General Ledger Profile. |
| **AccountType** | **string** | Required | The account type attributed to the record. |
| **LocalCurrency** | **string** | Required | The local currency for the amounts specified. Defaults to base currency if multiple different currencies present in the grouped line. |
| **Opening** | [MultiCurrencyAmounts](MultiCurrencyAmounts.md) | Required | *No description available.* |
| **Closing** | [MultiCurrencyAmounts](MultiCurrencyAmounts.md) | Required | *No description available.* |
| **Debit** | [MultiCurrencyAmounts](MultiCurrencyAmounts.md) | Required | *No description available.* |
| **Credit** | [MultiCurrencyAmounts](MultiCurrencyAmounts.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Properties found on the mapped &#39;Account&#39;, as specified in request. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TrialBalance(
    generalLedgerAccountCode: "...",  // required — The Account code that the trial balance results have been grouped against.
    description: "...",  // optional — The description of the record.
    levels: ,  // required — The levels that have been derived from the specified General Ledger Profile.
    accountType: "...",  // required — The account type attributed to the record.
    localCurrency: "...",  // required — The local currency for the amounts specified. Defaults to base currency if multiple different currencies present in the grouped line.
    opening: new MultiCurrencyAmounts(...),  // required
    closing: new MultiCurrencyAmounts(...),  // required
    debit: new MultiCurrencyAmounts(...),  // required
    credit: new MultiCurrencyAmounts(...),  // required
    properties: new Property(...),  // optional — Properties found on the mapped &#39;Account&#39;, as specified in request.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TrialBalance>(json);
```

- [MultiCurrencyAmounts](MultiCurrencyAmounts.md)
- [MultiCurrencyAmounts](MultiCurrencyAmounts.md)
- [MultiCurrencyAmounts](MultiCurrencyAmounts.md)
- [MultiCurrencyAmounts](MultiCurrencyAmounts.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

