# Finbourne.Sdk.Lusid.Model.InstrumentPaymentDiaryLeg

A leg containing a set of cashflows.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LegIndex** | **int** | Optional | Index (integer) for the leg of a payment diary. |
| **LegId** | **string** | Optional | Identifier string for the leg of a payment diary. |
| **Rows** | [List&lt;InstrumentPaymentDiaryRow&gt;](InstrumentPaymentDiaryRow.md) | Optional | List of individual cashflows within the payment diary. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentPaymentDiaryLeg(
    legIndex: 0,  // optional — Index (integer) for the leg of a payment diary.
    legId: "...",  // optional — Identifier string for the leg of a payment diary.
    rows: new List<InstrumentPaymentDiaryRow>()  // optional — List of individual cashflows within the payment diary.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentPaymentDiaryLeg>(json);
```

- [InstrumentPaymentDiaryRow](InstrumentPaymentDiaryRow.md) — used in `Rows`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

