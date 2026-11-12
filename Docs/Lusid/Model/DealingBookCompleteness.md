# Finbourne.Sdk.Lusid.Model.DealingBookCompleteness

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Complete** | **bool** | Required | Whether every share class&#39;s dealing cut-off had passed at the strike&#39;s as-at. True when no cut-off is configured. |
| **CutOff** | **DateTimeOffset?** | Optional | The latest dealing cut-off among the share classes that configure one. Absent when none does. |
| **LateNotCounted** | **int?** | Optional | How many orders at the valuation point were written to the book after their class&#39;s cut-off and so were reported but not counted. Absent when a cut-off is configured but lateness could not be judged because an order at the valuation point carries no version. |
| **Note** | **string** | Optional | Why the book was judged complete or incomplete: the cut-off that had or had not passed, or that none is configured and completeness was assumed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DealingBookCompleteness(
    complete: true,  // required — Whether every share class&#39;s dealing cut-off had passed at the strike&#39;s as-at. True when no cut-off is configured.
    cutOff: DateTimeOffset.Now,  // optional — The latest dealing cut-off among the share classes that configure one. Absent when none does.
    lateNotCounted: 0,  // optional — How many orders at the valuation point were written to the book after their class&#39;s cut-off and so were reported but not counted. Absent when a cut-off is configured but lateness could not be judged because an order at the valuation point carries no version.
    note: "..."  // optional — Why the book was judged complete or incomplete: the cut-off that had or had not passed, or that none is configured and completeness was assumed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DealingBookCompleteness>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

