# Finbourne.Sdk.Luminesce.Model.IntellisenseItem

Representation of an item in an Intellisense popup
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Caption** | **string** | Required | The value to show the user in the popup |
| **Value** | **string** | Required | The value to substitute in |
| **Meta** | **string** | Optional | The light-grey text shown to the right of the Caption in the popup |
| **Score** | **int** | Optional | How important is this.  Bigger is more important. |
| **DocHTML** | **string** | Optional | Popup further info (as in a whole documentation article!) |
| **Type** | **IntellisenseType** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new IntellisenseItem(
    caption: "...",  // required — The value to show the user in the popup
    value: "...",  // required — The value to substitute in
    meta: "...",  // optional — The light-grey text shown to the right of the Caption in the popup
    score: 0,  // optional — How important is this.  Bigger is more important.
    docHTML: "...",  // optional — Popup further info (as in a whole documentation article!)
    type:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntellisenseItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

