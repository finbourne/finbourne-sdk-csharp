# Finbourne.Sdk.Lusid.Model.ExternalRecType

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name for this external reconciliation describing source data. |
| **Temporality** | **string** | Optional | How the reconciliation reads its data: PointInTime (the latest state as at the instance&#39;s effectiveAt, the default) or Activity (everything effective across the instance&#39;s activity window). Available values: PointInTime, Activity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExternalRecType(
    name: "...",  // required — The name for this external reconciliation describing source data.
    temporality: "..."  // optional — How the reconciliation reads its data: PointInTime (the latest state as at the instance&#39;s effectiveAt, the default) or Activity (everything effective across the instance&#39;s activity window). Available values: PointInTime, Activity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalRecType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

