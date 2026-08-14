# Finbourne.Sdk.Lusid.Model.RecResultItemDetails

The individual items that make up a rec result, split by side. Zero counts and empty arrays for  results that have cleared.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CountLeft** | **int** | Required | The number of items grouped on the left side. |
| **CountRight** | **int** | Required | The number of items grouped on the right side. |
| **Left** | [List&lt;RecResultItem&gt;](RecResultItem.md) | Optional | The left-side items. |
| **Right** | [List&lt;RecResultItem&gt;](RecResultItem.md) | Optional | The right-side items. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultItemDetails(
    countLeft: 0,  // required — The number of items grouped on the left side.
    countRight: 0,  // required — The number of items grouped on the right side.
    left: new List<RecResultItem>(),  // optional — The left-side items.
    right: new List<RecResultItem>()  // optional — The right-side items.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultItemDetails>(json);
```

- [RecResultItem](RecResultItem.md) — used in `Left`
- [RecResultItem](RecResultItem.md) — used in `Right`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

