# Finbourne.Sdk.Insights.Model.TimeRange

A server-resolved time window for a query, as an alternative to supplying absolute StartAt/EndAt. Supply either a Finbourne.Insights.WebApi.Dtos.Querying.TimeRange.Preset (e.g. LastWeek, CurrentMonth) or a relative range via Finbourne.Insights.WebApi.Dtos.Querying.TimeRange.From and Finbourne.Insights.WebApi.Dtos.Querying.TimeRange.To. The window is resolved on the server at query time, so a saved query re-runs against a sliding window. Calendar boundaries are anchored in Finbourne.Insights.WebApi.Dtos.Querying.TimeRange.TimeZone (default UTC); weeks start on Monday.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Preset** | **string** | Optional | A named preset window. One of the Finbourne.Insights.WebApi.Dtos.Querying.TimeRangePreset values. Mutually exclusive with Finbourne.Insights.WebApi.Dtos.Querying.TimeRange.From/Finbourne.Insights.WebApi.Dtos.Querying.TimeRange.To. |
| **From** | [RelativeBoundary](RelativeBoundary.md) | Optional | *No description available.* |
| **To** | [RelativeBoundary](RelativeBoundary.md) | Optional | *No description available.* |
| **VarTimeZone** | **string** | Optional | Optional IANA time-zone identifier (e.g. \&quot;Europe/London\&quot;) used to anchor calendar boundaries (start of day/week/month/quarter/year). Defaults to UTC when not supplied. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new TimeRange(
    preset: "...",  // optional — A named preset window. One of the Finbourne.Insights.WebApi.Dtos.Querying.TimeRangePreset values. Mutually exclusive with Finbourne.Insights.WebApi.Dtos.Querying.TimeRange.From/Finbourne.Insights.WebApi.Dtos.Querying.TimeRange.To.
    from: new RelativeBoundary(...),  // optional
    to: new RelativeBoundary(...),  // optional
    varTimeZone: "..."  // optional — Optional IANA time-zone identifier (e.g. \&quot;Europe/London\&quot;) used to anchor calendar boundaries (start of day/week/month/quarter/year). Defaults to UTC when not supplied.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TimeRange>(json);
```

- [RelativeBoundary](RelativeBoundary.md)
- [RelativeBoundary](RelativeBoundary.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

