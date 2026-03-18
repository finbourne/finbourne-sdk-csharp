# Finbourne.Sdk.Lusid.Model.GeneralLedgerProfileMapping

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MappingFilter** | **string** | Required | The filter syntax for the Mapping filter. See https://support.lusid.com/knowledgebase/article/KA-02140 for more information on filter syntax |
| **Levels** | **List&lt;string&gt;** | Required | References fields and properties on the associated Journal Entry Line and graph of associated objects. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GeneralLedgerProfileMapping(
    mappingFilter: "...",  // required — The filter syntax for the Mapping filter. See https://support.lusid.com/knowledgebase/article/KA-02140 for more information on filter syntax
    levels:   // required — References fields and properties on the associated Journal Entry Line and graph of associated objects.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GeneralLedgerProfileMapping>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

