# Finbourne.Sdk.Lusid.Model.InstrumentDefinitionFormat

What is the provenance of an instrument. This defines who creates/owns it, what format it is in (e.g. a proprietary format or a common and known one)              and what the version of that is.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourceSystem** | **string** | Required | which source system does the format originate from |
| **Vendor** | **string** | Required | An instrument will potentially have been created by any number of different organisations. Some will be understood completely (e.g. LUSID&#39;s), some won&#39;t.              The provenance of an instrument indicates who \&quot;owns\&quot; the associated format. |
| **VarVersion** | **string** | Required | Version of the document. Would be preferable to avoid the need, but LUSID will not control other organisations&#39; trade formats. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentDefinitionFormat(
    sourceSystem: "...",  // required — which source system does the format originate from
    vendor: "...",  // required — An instrument will potentially have been created by any number of different organisations. Some will be understood completely (e.g. LUSID&#39;s), some won&#39;t.              The provenance of an instrument indicates who \&quot;owns\&quot; the associated format.
    varVersion: "..."  // required — Version of the document. Would be preferable to avoid the need, but LUSID will not control other organisations&#39; trade formats.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentDefinitionFormat>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

