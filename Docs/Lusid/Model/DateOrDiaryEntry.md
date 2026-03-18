# Finbourne.Sdk.Lusid.Model.DateOrDiaryEntry

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | A date. If specified, DiaryEntry must not be specified. |
| **DiaryEntry** | **string** | Optional | The code of a diary entry. If specified, Date must not be specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DateOrDiaryEntry(
    date: new DateTimeOrCutLabel(...),  // optional — A date. If specified, DiaryEntry must not be specified.
    diaryEntry: "..."  // optional — The code of a diary entry. If specified, Date must not be specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DateOrDiaryEntry>(json);
```


## Related Models

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `Date`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

