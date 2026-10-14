# Finbourne.Sdk.Lusid.Model.AllocationMapIlpaTransactionType

The ILPA transaction type an Allocation Map reports one kind of allocation event under, overriding the default.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EventType** | **string** | Required | The kind of allocation event the ILPA transaction type applies to: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default or Commitment. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove, Commitment, Equalisation, RecallExpiry, Transfer, Default, DealFunding. |
| **IlpaTransactionType** | **string** | Required | The ILPA transaction type events of this kind are reported under, for example &#39;Capital Call: Investments&#39; or &#39;Distribution: Recallable&#39;. Must be a value of the system IlpaTransactionType data type. |
| **Component** | **string** | Optional | The component of the event the ILPA transaction type applies to, for example MgmtFee or ROC. Absent means the entry is the default for every component of the event type without an entry of its own. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapIlpaTransactionType(
    eventType: "...",  // required — The kind of allocation event the ILPA transaction type applies to: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default or Commitment. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove, Commitment, Equalisation, RecallExpiry, Transfer, Default, DealFunding.
    ilpaTransactionType: "...",  // required — The ILPA transaction type events of this kind are reported under, for example &#39;Capital Call: Investments&#39; or &#39;Distribution: Recallable&#39;. Must be a value of the system IlpaTransactionType data type.
    component: "..."  // optional — The component of the event the ILPA transaction type applies to, for example MgmtFee or ROC. Absent means the entry is the default for every component of the event type without an entry of its own.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapIlpaTransactionType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

