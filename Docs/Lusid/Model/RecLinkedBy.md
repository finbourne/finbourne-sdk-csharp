# Finbourne.Sdk.Lusid.Model.RecLinkedBy

The item keys a link between two rec results was established on, per side.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [List&lt;RecLinkKey&gt;](RecLinkKey.md) | Required | The keys shared by the two results&#39; left-side items. May be empty. |
| **Right** | [List&lt;RecLinkKey&gt;](RecLinkKey.md) | Required | The keys shared by the two results&#39; right-side items. May be empty. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecLinkedBy(
    left: new List<RecLinkKey>(),  // required — The keys shared by the two results&#39; left-side items. May be empty.
    right: new List<RecLinkKey>()  // required — The keys shared by the two results&#39; right-side items. May be empty.
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

- [RecLinkKey](RecLinkKey.md) — used in `Left`
- [RecLinkKey](RecLinkKey.md) — used in `Right`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

