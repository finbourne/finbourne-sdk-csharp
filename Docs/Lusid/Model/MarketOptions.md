# Finbourne.Sdk.Lusid.Model.MarketOptions

The set of options that control miscellaneous and default market resolution behaviour.  These are aimed at a 'crude' level of control for those who do not wish to fine tune the way that data is resolved.  For clients who wish to simply match instruments to prices this is quite possibly sufficient. For those wishing to control market data sources  according to requirements based on accuracy or timeliness it is not. In more advanced cases the options should largely be ignored and rules specified  per source. Be aware that where no specified rule matches the final fallback is on to the logic implied here.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DefaultSupplier** | **string** | Optional | The default supplier of data. This controls which &#39;dialect&#39; is used to find particular market data. e.g. one supplier might address data by RIC, another by PermId |
| **DefaultInstrumentCodeType** | **string** | Optional | When instrument quotes are searched for, what identifier should be used by default |
| **DefaultScope** | **string** | Required | For default rules, which scope should data be searched for in |
| **AttemptToInferMissingFx** | **bool** | Optional | if true will calculate a missing Fx pair (e.g. THBJPY) from the inverse JPYTHB or from standardised pairs against USD, e.g. THBUSD and JPYUSD |
| **CalendarScope** | **string** | Optional | The scope in which holiday calendars stored |
| **ConventionScope** | **string** | Optional | The scope in which conventions stored |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarketOptions(
    defaultSupplier: "...",  // optional — The default supplier of data. This controls which &#39;dialect&#39; is used to find particular market data. e.g. one supplier might address data by RIC, another by PermId
    defaultInstrumentCodeType: "...",  // optional — When instrument quotes are searched for, what identifier should be used by default
    defaultScope: "...",  // required — For default rules, which scope should data be searched for in
    attemptToInferMissingFx: true,  // optional — if true will calculate a missing Fx pair (e.g. THBJPY) from the inverse JPYTHB or from standardised pairs against USD, e.g. THBUSD and JPYUSD
    calendarScope: "...",  // optional — The scope in which holiday calendars stored
    conventionScope: "..."  // optional — The scope in which conventions stored
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarketOptions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

