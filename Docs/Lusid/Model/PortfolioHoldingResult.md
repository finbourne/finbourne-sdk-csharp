# Finbourne.Sdk.Lusid.Model.PortfolioHoldingResult

Represents holding details for a data quality check result, where LusidEntityResult represents a scope-and-code  or identifier-addressed entity. A holding has no scope and code of its own, so it is identified by the portfolio  it came from plus what distinguishes it within that portfolio.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Optional | The type of the entity. Always \&quot;Holding\&quot;. |
| **AsAt** | **DateTimeOffset** | Optional | The as-at timestamp for the holding |
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective-at timestamp for the holding |
| **SourcePortfolioScope** | **string** | Optional | The scope of the portfolio this holding came from |
| **SourcePortfolioCode** | **string** | Optional | The code of the portfolio this holding came from |
| **SourcePortfolioEntityUniqueId** | **string** | Optional | The unique identifier of the portfolio this holding came from |
| **SourcePortfolioDisplayName** | **string** | Optional | The display name of the portfolio this holding came from |
| **HoldingId** | **string** | Optional | The holding&#39;s identifier within its portfolio |
| **TaxlotId** | **string** | Optional | The tax lot identifier, where the holding was expanded to tax lots. Null otherwise. |
| **SubEntityId** | **string** | Optional | Identifies the holding to the derived property explain API: the holding id on its own, or the holding id  and tax lot id colon-separated where a tax lot is present. |
| **LusidInstrumentId** | **string** | Optional | The LUSID instrument identifier of the instrument held |
| **InstrumentDisplayName** | **string** | Optional | The name of the instrument held |
| **HoldingTypeName** | **string** | Optional | The kind of holding, e.g. Position, Balance |
| **Currency** | **string** | Optional | The currency of the holding |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioHoldingResult(
    entityType: "...",  // optional — The type of the entity. Always \&quot;Holding\&quot;.
    asAt: DateTimeOffset.Now,  // optional — The as-at timestamp for the holding
    effectiveAt: DateTimeOffset.Now,  // optional — The effective-at timestamp for the holding
    sourcePortfolioScope: "...",  // optional — The scope of the portfolio this holding came from
    sourcePortfolioCode: "...",  // optional — The code of the portfolio this holding came from
    sourcePortfolioEntityUniqueId: "...",  // optional — The unique identifier of the portfolio this holding came from
    sourcePortfolioDisplayName: "...",  // optional — The display name of the portfolio this holding came from
    holdingId: "...",  // optional — The holding&#39;s identifier within its portfolio
    taxlotId: "...",  // optional — The tax lot identifier, where the holding was expanded to tax lots. Null otherwise.
    subEntityId: "...",  // optional — Identifies the holding to the derived property explain API: the holding id on its own, or the holding id  and tax lot id colon-separated where a tax lot is present.
    lusidInstrumentId: "...",  // optional — The LUSID instrument identifier of the instrument held
    instrumentDisplayName: "...",  // optional — The name of the instrument held
    holdingTypeName: "...",  // optional — The kind of holding, e.g. Position, Balance
    currency: "..."  // optional — The currency of the holding
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioHoldingResult>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

