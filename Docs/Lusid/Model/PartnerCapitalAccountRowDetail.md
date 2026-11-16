# Finbourne.Sdk.Lusid.Model.PartnerCapitalAccountRowDetail

One labelled part of a capital account row's total: the kind of amount, the allocation event it arose on and its  quarter-, year- and inception-to-date amounts, each already included in the row's own column.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Kind** | **string** | Required | The kind of amount the entry labels: WithholdingTax for tax withheld from a distribution on the partner&#39;s behalf. |
| **AllocationEventId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EventDate** | **DateTimeOffset** | Required | The effective date of the allocation event the amount arose on. |
| **Qtd** | **decimal** | Required | The part of the row&#39;s quarter-to-date amount the entry labels; zero when the event falls outside the quarter. |
| **Ytd** | **decimal** | Required | The part of the row&#39;s year-to-date amount the entry labels; zero when the event falls outside the year. |
| **Itd** | **decimal** | Required | The part of the row&#39;s inception-to-date amount the entry labels. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerCapitalAccountRowDetail(
    kind: "...",  // required — The kind of amount the entry labels: WithholdingTax for tax withheld from a distribution on the partner&#39;s behalf.
    allocationEventId: new ResourceId(...),  // required
    eventDate: DateTimeOffset.Now,  // required — The effective date of the allocation event the amount arose on.
    qtd: 0.0d,  // required — The part of the row&#39;s quarter-to-date amount the entry labels; zero when the event falls outside the quarter.
    ytd: 0.0d,  // required — The part of the row&#39;s year-to-date amount the entry labels; zero when the event falls outside the year.
    itd: 0.0d  // required — The part of the row&#39;s inception-to-date amount the entry labels.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerCapitalAccountRowDetail>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

