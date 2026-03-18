# Finbourne.Sdk.Lusid.Model.CreateClosedPeriodRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ClosedPeriodId** | **string** | Required | The unique Id of the Closed Period. The ClosedPeriodId, together with the Timeline Scope and Code, uniquely identifies a Closed Period |
| **EffectiveEnd** | **DateTimeOffset** | Optional | The effective end of the Closed Period |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The Closed Periods properties. These will be from the &#39;ClosedPeriod&#39; domain. |
| **AsAtClosed** | **DateTimeOffset?** | Optional | The asAt closed datetime for the Closed Period |
| **DisplayName** | **string** | Optional | The name of the Closed Period. |
| **Description** | **string** | Optional | A description for the Closed Period. |
| **HoldingsAsAtClosedOverride** | **DateTimeOffset?** | Optional | The optional AsAtClosed Override to use for building holdings in the Closed Period.If not specified, the AsAtClosed on the Closed Period will be used. |
| **ValuationAsAtClosedOverride** | **DateTimeOffset?** | Optional | The optional AsAtClosed Override to use for performing valuations in the Closed Period.If not specified, the AsAtClosed on the Closed Period will be used. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateClosedPeriodRequest(
    closedPeriodId: "...",  // required — The unique Id of the Closed Period. The ClosedPeriodId, together with the Timeline Scope and Code, uniquely identifies a Closed Period
    effectiveEnd: DateTimeOffset.Now,  // optional — The effective end of the Closed Period
    properties: new Property(...),  // optional — The Closed Periods properties. These will be from the &#39;ClosedPeriod&#39; domain.
    asAtClosed: DateTimeOffset.Now,  // optional — The asAt closed datetime for the Closed Period
    displayName: "...",  // optional — The name of the Closed Period.
    description: "...",  // optional — A description for the Closed Period.
    holdingsAsAtClosedOverride: DateTimeOffset.Now,  // optional — The optional AsAtClosed Override to use for building holdings in the Closed Period.If not specified, the AsAtClosed on the Closed Period will be used.
    valuationAsAtClosedOverride: DateTimeOffset.Now  // optional — The optional AsAtClosed Override to use for performing valuations in the Closed Period.If not specified, the AsAtClosed on the Closed Period will be used.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateClosedPeriodRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

