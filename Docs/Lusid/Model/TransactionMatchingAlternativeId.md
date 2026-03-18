# Finbourne.Sdk.Lusid.Model.TransactionMatchingAlternativeId

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PropertyKey** | **string** | Required | An property key (from the &#39;Transaction&#39; domain) that can be used as an alternative to TransactionId when matching transactions to settlement instructions. This property must be pre-defined and must be present on the transaction in order to be used for matching. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionMatchingAlternativeId(
    propertyKey: "..."  // required — An property key (from the &#39;Transaction&#39; domain) that can be used as an alternative to TransactionId when matching transactions to settlement instructions. This property must be pre-defined and must be present on the transaction in order to be used for matching.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionMatchingAlternativeId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

