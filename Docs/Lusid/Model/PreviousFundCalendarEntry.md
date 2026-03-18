# Finbourne.Sdk.Lusid.Model.PreviousFundCalendarEntry

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The unique Code of the Calendar Entry. The Calendar Entry, together with the Fund Scope and Code, uniquely identifies a Fund Calendar Entry. |
| **DisplayName** | **string** | Required | The name of the Fund Calendar entry. |
| **Description** | **string** | Optional | A description for the Fund Calendar entry. |
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective at of the Calendar Entry. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime for the Calendar Entry. |
| **HoldingsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest. |
| **ValuationsAsAtOverride** | **DateTimeOffset?** | Optional | The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PreviousFundCalendarEntry(
    code: "...",  // required — The unique Code of the Calendar Entry. The Calendar Entry, together with the Fund Scope and Code, uniquely identifies a Fund Calendar Entry.
    displayName: "...",  // required — The name of the Fund Calendar entry.
    description: "...",  // optional — A description for the Fund Calendar entry.
    effectiveAt: DateTimeOffset.Now,  // optional — The effective at of the Calendar Entry.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime for the Calendar Entry.
    holdingsAsAtOverride: DateTimeOffset.Now,  // optional — The optional AsAt Override to use for building holdings in the Valuation Point. Defaults to Latest.
    valuationsAsAtOverride: DateTimeOffset.Now  // optional — The optional AsAt Override to use for performing valuations in the Valuation Point. Defaults to Latest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PreviousFundCalendarEntry>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

