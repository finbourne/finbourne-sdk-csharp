# Finbourne.Sdk.Lusid.Model.RecLinkedBy

The item pairings a link between two rec results was established on, per side.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [List&lt;RecResultLinkKey&gt;](RecResultLinkKey.md) | Required | The pairings between the two results&#39; left-side items, one entry per pairing. May be empty. |
| **Right** | [List&lt;RecResultLinkKey&gt;](RecResultLinkKey.md) | Required | The pairings between the two results&#39; right-side items, one entry per pairing. May be empty. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecLinkedBy(
    left: new List<RecResultLinkKey>(),  // required — The pairings between the two results&#39; left-side items, one entry per pairing. May be empty.
    right: new List<RecResultLinkKey>()  // required — The pairings between the two results&#39; right-side items, one entry per pairing. May be empty.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecLinkedBy>(json);
```


## Related Models

- [RecResultLinkKey](RecResultLinkKey.md) — used in `Left`
- [RecResultLinkKey](RecResultLinkKey.md) — used in `Right`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

