# Finbourne.Sdk.Lusid.Model.AllocationEventTransferConsideration

The consideration paid for a transferred capital interest.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **decimal** | Required | The consideration amount. |
| **Currency** | **string** | Required | The ISO 4217 code of the currency of the consideration. |
| **RecordOnly** | **bool** | Optional | Whether the consideration is recorded for reference only, with no cash movement booked. Defaults to false. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventTransferConsideration(
    amount: 0.0d,  // required — The consideration amount.
    currency: "...",  // required — The ISO 4217 code of the currency of the consideration.
    recordOnly: true  // optional — Whether the consideration is recorded for reference only, with no cash movement booked. Defaults to false.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventTransferConsideration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

