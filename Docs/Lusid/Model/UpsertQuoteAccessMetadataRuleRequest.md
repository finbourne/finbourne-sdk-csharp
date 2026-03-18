# Finbourne.Sdk.Lusid.Model.UpsertQuoteAccessMetadataRuleRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [QuoteAccessMetadataRuleId](QuoteAccessMetadataRuleId.md) | Required | *No description available.* |
| **Metadata** | **Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt;** | Required | The access control metadata to assign to quotes that match the identifier |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertQuoteAccessMetadataRuleRequest(
    id: new QuoteAccessMetadataRuleId(...),  // required
    metadata:   // required — The access control metadata to assign to quotes that match the identifier
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertQuoteAccessMetadataRuleRequest>(json);
```


## Related Models

- [QuoteAccessMetadataRuleId](QuoteAccessMetadataRuleId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

