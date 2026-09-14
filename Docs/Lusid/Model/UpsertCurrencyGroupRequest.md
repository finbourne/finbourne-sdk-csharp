# Finbourne.Sdk.Lusid.Model.UpsertCurrencyGroupRequest

Request body for creating or updating a currency group.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the currency group. This uniquely identifies the currency group within the tenant. |
| **DisplayName** | **string** | Required | The name of the currency group. |
| **Description** | **string** | Optional | A description for the currency group. |
| **MajorUnitCurrency** | **string** | Required | The three-letter, case-sensitive currency code of the group&#39;s major unit, e.g. GBP for the sterling group. |
| **CirculationDomain** | **string** | Optional | The domain in which the group&#39;s currencies circulate, e.g. an ISO 3166 country code. |
| **MinorUnits** | [List&lt;CurrencyGroupMinorUnit&gt;](CurrencyGroupMinorUnit.md) | Optional | The minor unit currencies belonging to this currency group. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertCurrencyGroupRequest(
    code: "...",  // required — The code of the currency group. This uniquely identifies the currency group within the tenant.
    displayName: "...",  // required — The name of the currency group.
    description: "...",  // optional — A description for the currency group.
    majorUnitCurrency: "...",  // required — The three-letter, case-sensitive currency code of the group&#39;s major unit, e.g. GBP for the sterling group.
    circulationDomain: "...",  // optional — The domain in which the group&#39;s currencies circulate, e.g. an ISO 3166 country code.
    minorUnits: new List<CurrencyGroupMinorUnit>()  // optional — The minor unit currencies belonging to this currency group.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertCurrencyGroupRequest>(json);
```

- [CurrencyGroupMinorUnit](CurrencyGroupMinorUnit.md) — used in `MinorUnits`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

