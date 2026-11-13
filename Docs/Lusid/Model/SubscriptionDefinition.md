# Finbourne.Sdk.Lusid.Model.SubscriptionDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | *No description available.* |
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TimelineId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TimelineProperty** | **string** | Optional | A portfolio property key (Portfolio/scope/code) naming a perpetual portfolio property whose value  (scope/code) identifies the timeline for each portfolio. Mutually exclusive with timelineId.  The property must be defined, with a data type of value type ResourceId or String. |
| **PortfolioFilter** | **string** | Optional | A filter, in the syntax of the list portfolios filter, that narrows a wildcard portfolioId to the portfolios  of the scope that match it. Only valid when portfolioId.code is \&quot;*\&quot;. It may use the portfolio&#39;s own fields and  its perpetual Portfolio properties; time-variant and derived properties and relationships are not supported.  A portfolio that starts or stops matching joins or leaves the subscription. |
| **AddressKeys** | **List&lt;string&gt;** | Optional | The set of addresses the subscriber wishes to receive. |
| **ByTaxLots** | **bool** | Optional | *No description available.* |
| **SubscriptionType** | **string** | Required | Required. The kind of data the subscription streams: before/after effects per  holding (holdings), the transactions themselves (transactions), or each changed holding&#39;s  complete current state (positions). Address keys and byTaxLots are not valid for a  transactions subscription. Available values: Holdings, Transactions, Positions. |
| **StartEffectiveAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **EndEffectiveAt** | **DateTimeOffset?** | Optional | Deprecated and no longer honoured: a fixed forward date stops being a forward view once  the live edge passes it. Use effectiveForwardDays instead. Still accepted and echoed back  so existing subscriptions keep round-tripping. |
| **EffectiveForwardDays** | **int?** | Optional | How far forward the subscription reports, as a number of calendar days past the live  edge — a rolling forward view that advances as time passes. |
| **InstrumentIdentifiers** | **List&lt;string&gt;** | Optional | The instrument identifiers each published holding carries, as Instrument/default/{type} property keys,  for example Instrument/default/ClientInternal. Each must name an instrument identifier type. At most 5.  Not valid for a transactions subscription. |
| **ReportCurrency** | **string** | Optional | The currency the report-currency values are given in, as a three-letter ISO code stored upper-case. Required  when addressKeys names any key other than the quantity, cost, current face, notional cost, variation margin  and currency keys: Holding/Units, Holding/SettledUnits, Holding/Cost/Dom, Holding/Cost/Pfolio,  Holding/CurrentFace, Holding/NotionalCost, Holding/VariationMargin, Holding/VariationMarginInPortfolioCcy,  Holding/HoldingType, Holding/DomCcy and Holding/PortfolioCcy. Not valid for a transactions subscription. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SubscriptionDefinition(
    scope: "...",  // required
    code: "...",  // required
    displayName: "...",  // optional
    description: "...",  // optional
    portfolioId: new ResourceId(...),  // required
    timelineId: new ResourceId(...),  // optional
    timelineProperty: "...",  // optional — A portfolio property key (Portfolio/scope/code) naming a perpetual portfolio property whose value  (scope/code) identifies the timeline for each portfolio. Mutually exclusive with timelineId.  The property must be defined, with a data type of value type ResourceId or String.
    portfolioFilter: "...",  // optional — A filter, in the syntax of the list portfolios filter, that narrows a wildcard portfolioId to the portfolios  of the scope that match it. Only valid when portfolioId.code is \&quot;*\&quot;. It may use the portfolio&#39;s own fields and  its perpetual Portfolio properties; time-variant and derived properties and relationships are not supported.  A portfolio that starts or stops matching joins or leaves the subscription.
    addressKeys: ,  // optional — The set of addresses the subscriber wishes to receive.
    byTaxLots: true,  // optional
    subscriptionType: "...",  // required — Required. The kind of data the subscription streams: before/after effects per  holding (holdings), the transactions themselves (transactions), or each changed holding&#39;s  complete current state (positions). Address keys and byTaxLots are not valid for a  transactions subscription. Available values: Holdings, Transactions, Positions.
    startEffectiveAt: DateTimeOffset.Now,  // optional
    endEffectiveAt: DateTimeOffset.Now,  // optional — Deprecated and no longer honoured: a fixed forward date stops being a forward view once  the live edge passes it. Use effectiveForwardDays instead. Still accepted and echoed back  so existing subscriptions keep round-tripping.
    effectiveForwardDays: 0,  // optional — How far forward the subscription reports, as a number of calendar days past the live  edge — a rolling forward view that advances as time passes.
    instrumentIdentifiers: ,  // optional — The instrument identifiers each published holding carries, as Instrument/default/{type} property keys,  for example Instrument/default/ClientInternal. Each must name an instrument identifier type. At most 5.  Not valid for a transactions subscription.
    reportCurrency: "..."  // optional — The currency the report-currency values are given in, as a three-letter ISO code stored upper-case. Required  when addressKeys names any key other than the quantity, cost, current face, notional cost, variation margin  and currency keys: Holding/Units, Holding/SettledUnits, Holding/Cost/Dom, Holding/Cost/Pfolio,  Holding/CurrentFace, Holding/NotionalCost, Holding/VariationMargin, Holding/VariationMarginInPortfolioCcy,  Holding/HoldingType, Holding/DomCcy and Holding/PortfolioCcy. Not valid for a transactions subscription.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SubscriptionDefinition>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

