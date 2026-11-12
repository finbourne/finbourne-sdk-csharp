# Finbourne.Sdk.Lusid.Model.FundTaxScope

The UK chargeable-gains tax scope of a fund at a point in time: the portfolios inside the regime and what the  regime's figures leave out.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Portfolios** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The portfolios within the UK chargeable-gains regime. A fund portfolio is in scope when its own details elect the regime. A NAV type that elects the regime puts its derived portfolio for each fund portfolio in scope. |
| **Exclusions** | [FundTaxScopeExclusions](FundTaxScopeExclusions.md) | Required | *No description available.* |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective datetime at which the tax scope was read. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime at which the tax scope was read. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundTaxScope(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    portfolios: new List<ResourceId>(),  // required — The portfolios within the UK chargeable-gains regime. A fund portfolio is in scope when its own details elect the regime. A NAV type that elects the regime puts its derived portfolio for each fund portfolio in scope.
    exclusions: new FundTaxScopeExclusions(...),  // required
    effectiveAt: DateTimeOffset.Now,  // required — The effective datetime at which the tax scope was read.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime at which the tax scope was read.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundTaxScope>(json);
```

- [ResourceId](ResourceId.md) — used in `Portfolios`
- [FundTaxScopeExclusions](FundTaxScopeExclusions.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

