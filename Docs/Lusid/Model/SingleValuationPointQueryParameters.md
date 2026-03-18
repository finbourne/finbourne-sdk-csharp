# Finbourne.Sdk.Lusid.Model.SingleValuationPointQueryParameters

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DateOrDiaryEntry** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Required | *No description available.* |
| **Variant** | **string** | Optional | Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SingleValuationPointQueryParameters(
    dateOrDiaryEntry: new DateOrDiaryEntry(...),  // required
    variant: "..."  // optional — Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SingleValuationPointQueryParameters>(json);
```


## Related Models

- [DateOrDiaryEntry](DateOrDiaryEntry.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

