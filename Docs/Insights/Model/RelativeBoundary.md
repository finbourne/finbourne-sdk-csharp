# Finbourne.Sdk.Insights.Model.RelativeBoundary

One end of a relative time range. Exactly one of the options must be set: Finbourne.Insights.WebApi.Dtos.Querying.RelativeBoundary.Now (the current instant), Finbourne.Insights.WebApi.Dtos.Querying.RelativeBoundary.Midnight (the start of the current day in the range's time zone), Finbourne.Insights.WebApi.Dtos.Querying.RelativeBoundary.Offset (a duration back from now) or Finbourne.Insights.WebApi.Dtos.Querying.RelativeBoundary.Absolute (an explicit instant).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Now** | **bool** | Optional | When &#x60;true&#x60;, this boundary is the current instant (\&quot;now\&quot;). |
| **Midnight** | **bool** | Optional | When &#x60;true&#x60;, this boundary is the start of the current day (midnight) in the range&#39;s time zone. |
| **Offset** | [RelativeOffset](RelativeOffset.md) | Optional | *No description available.* |
| **Absolute** | **DateTimeOffset?** | Optional | An explicit absolute instant. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new RelativeBoundary(
    now: true,  // optional — When &#x60;true&#x60;, this boundary is the current instant (\&quot;now\&quot;).
    midnight: true,  // optional — When &#x60;true&#x60;, this boundary is the start of the current day (midnight) in the range&#39;s time zone.
    offset: new RelativeOffset(...),  // optional
    absolute: DateTimeOffset.Now  // optional — An explicit absolute instant.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelativeBoundary>(json);
```

- [RelativeOffset](RelativeOffset.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

