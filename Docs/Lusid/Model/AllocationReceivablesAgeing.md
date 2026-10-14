# Finbourne.Sdk.Lusid.Model.AllocationReceivablesAgeing

What each investor still owes on a booked capital call as of a date, and how late it is.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsOf** | **DateTimeOffset** | Optional | The date the receivables are aged as of. |
| **DueDate** | **DateTimeOffset?** | Optional | The date the cash was due. |
| **Outstanding** | **decimal** | Optional | The total still owed across all investor records. |
| **Receivables** | [List&lt;AllocationReceivable&gt;](AllocationReceivable.md) | Optional | One entry per investor record that was called. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationReceivablesAgeing(
    asOf: DateTimeOffset.Now,  // optional — The date the receivables are aged as of.
    dueDate: DateTimeOffset.Now,  // optional — The date the cash was due.
    outstanding: 0.0d,  // optional — The total still owed across all investor records.
    receivables: new List<AllocationReceivable>()  // optional — One entry per investor record that was called.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationReceivablesAgeing>(json);
```

- [AllocationReceivable](AllocationReceivable.md) — used in `Receivables`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

