# Finbourne.Sdk.Lusid.Model.ValuationPointDataQueryParameters

The parameters used in getting the ValuationPointData.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Start** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Optional | *No description available.* |
| **End** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Required | *No description available.* |
| **Variant** | **string** | Optional | Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPointDataQueryParameters(
    start: new DateOrDiaryEntry(...),  // optional
    end: new DateOrDiaryEntry(...),  // required
    variant: "..."  // optional — Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPointDataQueryParameters>(json);
```


## Related Models

- [DateOrDiaryEntry](DateOrDiaryEntry.md)
- [DateOrDiaryEntry](DateOrDiaryEntry.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

