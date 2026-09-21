# Finbourne.Sdk.Lusid.Model.RecLinkKey

One item key that established a link between two rec results: the key name and the identifier value both  results' items carried for it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key name: holdingId or transactionId. |
| **Value** | **string** | Required | The identifier value both results&#39; items carried under the key. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecLinkKey(
    key: "...",  // required — The key name: holdingId or transactionId.
    value: "..."  // required — The identifier value both results&#39; items carried under the key.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecLinkKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

