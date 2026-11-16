# Finbourne.Sdk.Lusid.Model.UnmatchedBreakdown

What a reserved unmatched sub-bucket holds: the amount routed to it and how many journal entry lines matched no  bucket filter to produce it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NoFilterMatch** | **decimal** | Required | The amount in the bucket over the period from journal entry lines that matched no bucket&#39;s filter. |
| **NoFilterMatchCount** | **int** | Required | How many journal entry lines produced that amount. On a share class node it counts the lines booked to the class and the fund-level and allocation group lines it takes a share of; on the fund node it counts every line once. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnmatchedBreakdown(
    noFilterMatch: 0.0d,  // required — The amount in the bucket over the period from journal entry lines that matched no bucket&#39;s filter.
    noFilterMatchCount: 0  // required — How many journal entry lines produced that amount. On a share class node it counts the lines booked to the class and the fund-level and allocation group lines it takes a share of; on the fund node it counts every line once.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnmatchedBreakdown>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

