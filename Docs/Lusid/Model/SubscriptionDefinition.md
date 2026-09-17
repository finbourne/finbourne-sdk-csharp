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
| **AddressKeys** | **List&lt;string&gt;** | Optional | The set of addresses the subscriber wishes to receive. |
| **ByTaxLots** | **bool** | Optional | *No description available.* |
| **SubscriptionType** | **string** | Optional | The kind of data the subscription streams (holdings or transactions), defaulting to holdings.  Address keys and byTaxLots are not valid for a transactions subscription. Available values: Holdings, Transactions. |
| **StartEffectiveAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **EndEffectiveAt** | **DateTimeOffset?** | Optional | Deprecated and no longer honoured: a fixed forward date stops being a forward view once  the live edge passes it. Use effectiveForwardDays instead. Still accepted and echoed back  so existing subscriptions keep round-tripping. |
| **EffectiveForwardDays** | **int?** | Optional | How far forward the subscription reports, as a number of calendar days past the live  edge — a rolling forward view that advances as time passes. |


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
    addressKeys: ,  // optional — The set of addresses the subscriber wishes to receive.
    byTaxLots: true,  // optional
    subscriptionType: "...",  // optional — The kind of data the subscription streams (holdings or transactions), defaulting to holdings.  Address keys and byTaxLots are not valid for a transactions subscription. Available values: Holdings, Transactions.
    startEffectiveAt: DateTimeOffset.Now,  // optional
    endEffectiveAt: DateTimeOffset.Now,  // optional — Deprecated and no longer honoured: a fixed forward date stops being a forward view once  the live edge passes it. Use effectiveForwardDays instead. Still accepted and echoed back  so existing subscriptions keep round-tripping.
    effectiveForwardDays: 0  // optional — How far forward the subscription reports, as a number of calendar days past the live  edge — a rolling forward view that advances as time passes.
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

