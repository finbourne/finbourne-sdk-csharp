# Finbourne.Sdk.Lusid.Model.AggregatedReturn

A list of Aggregated Returns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Required | The effectiveAt for the return. |
| **EndOfPeriod** | **DateTimeOffset** | Required | The end of period date. For the monthly period this will be the Month End Date. |
| **OpeningMarketValue** | **decimal?** | Optional | The opening market value. |
| **ClosingMarketValue** | **decimal?** | Optional | The closing market value. |
| **MetricsValue** | **Dictionary&lt;string, decimal&gt;** | Required | The value for the specified metric. |
| **Frequency** | **string** | Optional | Show the aggregated output returns on a Daily or Monthly period. |
| **CompositeMembers** | **int?** | Optional | The number of members in the Composite on the given day. |
| **CompositeMembersWithoutReturn** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | List containing Composite members which post no return on the given day. |
| **Warnings** | **List&lt;string&gt;** | Optional | List of the warnings about the calculation of the aggregated return. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregatedReturn(
    effectiveAt: DateTimeOffset.Now,  // required — The effectiveAt for the return.
    endOfPeriod: DateTimeOffset.Now,  // required — The end of period date. For the monthly period this will be the Month End Date.
    openingMarketValue: 0.0d,  // optional — The opening market value.
    closingMarketValue: 0.0d,  // optional — The closing market value.
    metricsValue: ,  // required — The value for the specified metric.
    frequency: "...",  // optional — Show the aggregated output returns on a Daily or Monthly period.
    compositeMembers: 0,  // optional — The number of members in the Composite on the given day.
    compositeMembersWithoutReturn: new List<ResourceId>(),  // optional — List containing Composite members which post no return on the given day.
    warnings:   // optional — List of the warnings about the calculation of the aggregated return.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregatedReturn>(json);
```

- [ResourceId](ResourceId.md) — used in `CompositeMembersWithoutReturn`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

