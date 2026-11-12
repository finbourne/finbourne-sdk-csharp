# Finbourne.Sdk.Lusid.Model.AllocationReceivablesAgeing

What each investor still owes on a booked capital call as of a date, and how late it is.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsOf** | **DateTimeOffset** | Optional | The date the receivables are aged as of. |
| **DueDate** | **DateTimeOffset?** | Optional | The date the cash was due. |
| **Outstanding** | **decimal** | Optional | What the investors still owe, looking through feeders to their LPs so a roll-up is not counted twice. |
| **Receivables** | [List&lt;AllocationReceivable&gt;](AllocationReceivable.md) | Optional | One entry per investor record and side that was called on a register. |
| **Registers** | [List&lt;AllocationRegisterReceivable&gt;](AllocationRegisterReceivable.md) | Optional | What each register is owed on its own lines, a feeder&#39;s roll-up included. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationReceivablesAgeing(
    asOf: DateTimeOffset.Now,  // optional — The date the receivables are aged as of.
    dueDate: DateTimeOffset.Now,  // optional — The date the cash was due.
    outstanding: 0.0d,  // optional — What the investors still owe, looking through feeders to their LPs so a roll-up is not counted twice.
    receivables: new List<AllocationReceivable>(),  // optional — One entry per investor record and side that was called on a register.
    registers: new List<AllocationRegisterReceivable>()  // optional — What each register is owed on its own lines, a feeder&#39;s roll-up included.
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
- [AllocationRegisterReceivable](AllocationRegisterReceivable.md) — used in `Registers`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

