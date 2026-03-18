# Finbourne.Sdk.Lusid.Model.FlowConventionName

Representation of an abstract definition of a flow convention set consisting of currency, tenor and an index name (arbitrary string but likely something like \"IBOR\").
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Currency** | **string** | Required | Currency of the flow convention name. |
| **IndexName** | **string** | Optional | The index, if present, that is required. e.g. \&quot;IBOR\&quot;, \&quot;OIS\&quot; or \&quot;SONIA\&quot;. |
| **Tenor** | **string** | Required | Tenor for the convention name.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FlowConventionName(
    currency: "...",  // required — Currency of the flow convention name.
    indexName: "...",  // optional — The index, if present, that is required. e.g. \&quot;IBOR\&quot;, \&quot;OIS\&quot; or \&quot;SONIA\&quot;.
    tenor: "..."  // required — Tenor for the convention name.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FlowConventionName>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

