# Finbourne.Sdk.Lusid.Model.TimeZoneConventions

Provides information on the primary time zone of an instrument and optional cut labels  for defining times to be used by instrument events.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PrimaryTimeZone** | **string** | Required | The IANA time zone code for the instrument. |
| **StartOfDay** | **string** | Optional | A LUSID Cut Label code used for generating instrument events at a time other than local midnight. |
| **PrimaryMarketOpen** | **string** | Optional | A LUSID Cut Label code used for delaying the transaction time of certain instrument events until market open. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TimeZoneConventions(
    primaryTimeZone: "...",  // required — The IANA time zone code for the instrument.
    startOfDay: "...",  // optional — A LUSID Cut Label code used for generating instrument events at a time other than local midnight.
    primaryMarketOpen: "..."  // optional — A LUSID Cut Label code used for delaying the transaction time of certain instrument events until market open.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TimeZoneConventions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

