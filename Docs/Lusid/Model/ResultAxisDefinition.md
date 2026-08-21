# Finbourne.Sdk.Lusid.Model.ResultAxisDefinition

Describes one labelled axis of a matrix-shaped result (Result1D/Result2D), so consumers can  tell what the labels on that axis mean without opening each value.  A Result1D has a single Y axis; a Result2D has a Y (row) and an X (column) axis.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Axis** | **string** | Optional | Which axis of the result this describes: \&quot;Y\&quot; labels the rows (the only axis of a Result1D,  serialized as labelsY on the value); \&quot;X\&quot; labels the columns of a Result2D (labelsX). |
| **Name** | **string** | Optional | The display name of the axis, e.g. \&quot;Bucket\&quot; or \&quot;Expiry\&quot;. |
| **LabelType** | **string** | Optional | What kind of value the axis labels are drawn from, e.g. \&quot;Tenor\&quot;, \&quot;Date\&quot; or \&quot;Strike\&quot;.  Consumers can switch rendering on well-known values and fall back to showing labels verbatim. |
| **Description** | **string** | Optional | What the axis means for this result. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResultAxisDefinition(
    axis: "...",  // optional — Which axis of the result this describes: \&quot;Y\&quot; labels the rows (the only axis of a Result1D,  serialized as labelsY on the value); \&quot;X\&quot; labels the columns of a Result2D (labelsX).
    name: "...",  // optional — The display name of the axis, e.g. \&quot;Bucket\&quot; or \&quot;Expiry\&quot;.
    labelType: "...",  // optional — What kind of value the axis labels are drawn from, e.g. \&quot;Tenor\&quot;, \&quot;Date\&quot; or \&quot;Strike\&quot;.  Consumers can switch rendering on well-known values and fall back to showing labels verbatim.
    description: "..."  // optional — What the axis means for this result.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultAxisDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

