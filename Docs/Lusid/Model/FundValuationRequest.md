# Finbourne.Sdk.Lusid.Model.FundValuationRequest

Specification object for the parameters of a valuation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | The asAt date to use. |
| **Metrics** | [List&lt;AggregateSpec&gt;](AggregateSpec.md) | Required | The set of specifications to calculate or retrieve during the valuation and present in the results. For example:  AggregateSpec(&#39;Valuation/PV&#39;,&#39;Sum&#39;) for returning the PV (present value) of holdings  AggregateSpec(&#39;Holding/default/Units&#39;,&#39;Sum&#39;) for returning the units of holidays  AggregateSpec(&#39;Instrument/default/LusidInstrumentId&#39;,&#39;Value&#39;) for returning the Lusid Instrument identifier |
| **GroupBy** | **List&lt;string&gt;** | Optional | The set of items by which to perform grouping. This primarily matters when one or more of the metric operators is a mapping  that reduces set size, e.g. sum or proportion. The group-by statement determines the set of keys by which to break the results out. |
| **Filters** | [List&lt;PropertyFilter&gt;](PropertyFilter.md) | Optional | A set of filters to use to reduce the data found in a request. Equivalent to the &#39;where ...&#39; part of a Sql select statement.  For example, filter a set of values within a given range or matching a particular value. |
| **Sort** | [List&lt;OrderBySpec&gt;](OrderBySpec.md) | Optional | A (possibly empty/null) set of specifications for how to order the results. |
| **EquipWithSubtotals** | **bool** | Optional | Flag directing the Valuation call to populate the results with subtotals of aggregates. |
| **ReturnResultAsExpandedTypes** | **bool** | Optional | Financially meaningful results can be presented as either simple flat types or more complex expanded types.  For example, the present value (PV) of a holding could be represented either as a simple decimal (with currency implied)  or as a decimal-currency pair. This flag allows either representation to be returned. In the PV example,  the returned value would be the decimal-currency pair if this flag is true, or the decimal only if this flag is false. |
| **IncludeOrderFlow** | [OrderFlowConfiguration](OrderFlowConfiguration.md) | Optional | *No description available.* |
| **FundValuationSchedule** | [FundValuationSchedule](FundValuationSchedule.md) | Required | *No description available.* |
| **MarketDataOverrides** | [MarketDataOverrides](MarketDataOverrides.md) | Optional | *No description available.* |
| **CorporateActionSourceId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundValuationRequest(
    asAt: DateTimeOffset.Now,  // optional — The asAt date to use.
    metrics: new List<AggregateSpec>(),  // required — The set of specifications to calculate or retrieve during the valuation and present in the results. For example:  AggregateSpec(&#39;Valuation/PV&#39;,&#39;Sum&#39;) for returning the PV (present value) of holdings  AggregateSpec(&#39;Holding/default/Units&#39;,&#39;Sum&#39;) for returning the units of holidays  AggregateSpec(&#39;Instrument/default/LusidInstrumentId&#39;,&#39;Value&#39;) for returning the Lusid Instrument identifier
    groupBy: ,  // optional — The set of items by which to perform grouping. This primarily matters when one or more of the metric operators is a mapping  that reduces set size, e.g. sum or proportion. The group-by statement determines the set of keys by which to break the results out.
    filters: new List<PropertyFilter>(),  // optional — A set of filters to use to reduce the data found in a request. Equivalent to the &#39;where ...&#39; part of a Sql select statement.  For example, filter a set of values within a given range or matching a particular value.
    sort: new List<OrderBySpec>(),  // optional — A (possibly empty/null) set of specifications for how to order the results.
    equipWithSubtotals: true,  // optional — Flag directing the Valuation call to populate the results with subtotals of aggregates.
    returnResultAsExpandedTypes: true,  // optional — Financially meaningful results can be presented as either simple flat types or more complex expanded types.  For example, the present value (PV) of a holding could be represented either as a simple decimal (with currency implied)  or as a decimal-currency pair. This flag allows either representation to be returned. In the PV example,  the returned value would be the decimal-currency pair if this flag is true, or the decimal only if this flag is false.
    includeOrderFlow: new OrderFlowConfiguration(...),  // optional
    fundValuationSchedule: new FundValuationSchedule(...),  // required
    marketDataOverrides: new MarketDataOverrides(...),  // optional
    corporateActionSourceId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundValuationRequest>(json);
```

- [AggregateSpec](AggregateSpec.md) — used in `Metrics`
- [PropertyFilter](PropertyFilter.md) — used in `Filters`
- [OrderBySpec](OrderBySpec.md) — used in `Sort`
- [OrderFlowConfiguration](OrderFlowConfiguration.md)
- [FundValuationSchedule](FundValuationSchedule.md)
- [MarketDataOverrides](MarketDataOverrides.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

