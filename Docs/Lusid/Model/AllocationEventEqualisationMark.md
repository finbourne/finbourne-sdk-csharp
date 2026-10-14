# Finbourne.Sdk.Lusid.Model.AllocationEventEqualisationMark

A valuation move already allocated to the existing partners that the close re-trues to the admitted partners.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OriginMemberShortCode** | **string** | Required | The member of the structure the mark belongs to. |
| **Amount** | **decimal** | Required | The valuation move already allocated, in the event currency. Negative for a fall in value or an expense. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventEqualisationMark(
    originMemberShortCode: "...",  // required — The member of the structure the mark belongs to.
    amount: 0.0d  // required — The valuation move already allocated, in the event currency. Negative for a fall in value or an expense.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventEqualisationMark>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

