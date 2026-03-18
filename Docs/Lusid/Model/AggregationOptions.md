# Finbourne.Sdk.Lusid.Model.AggregationOptions

Options for controlling the default aspects and behaviour of the aggregation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UseAnsiLikeSyntax** | **bool** | Optional | Should the aggregation behave like ANSI Sql or MySql with respect to a conceptual request which is equivalent to \&quot;select a,sum(a) from results\&quot;;  ANSI Sql would report an error if a was not unique where MySql would simply view a,suma(a) as equivalent to firstof(a),sum(a). |
| **AllowPartialEntitlementSuccess** | **bool** | Optional | In the case of valuing a portfolio group where some, but not all entitlements fail, should the aggregation return the valuations  applied only to those portfolios where entitlements checks succeeded. |
| **ApplyIso4217Rounding** | **bool** | Optional | Various results that are units of currency might need to be rounded.  This will round according to the ISO4217 standard number of decimal places for a currency. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregationOptions(
    useAnsiLikeSyntax: true,  // optional — Should the aggregation behave like ANSI Sql or MySql with respect to a conceptual request which is equivalent to \&quot;select a,sum(a) from results\&quot;;  ANSI Sql would report an error if a was not unique where MySql would simply view a,suma(a) as equivalent to firstof(a),sum(a).
    allowPartialEntitlementSuccess: true,  // optional — In the case of valuing a portfolio group where some, but not all entitlements fail, should the aggregation return the valuations  applied only to those portfolios where entitlements checks succeeded.
    applyIso4217Rounding: true  // optional — Various results that are units of currency might need to be rounded.  This will round according to the ISO4217 standard number of decimal places for a currency.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregationOptions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

