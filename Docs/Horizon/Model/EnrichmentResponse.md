# Finbourne.Sdk.Horizon.Model.EnrichmentResponse

Collated enrichment result information
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EnrichedInstruments** | **List&lt;string&gt;** | Required | *No description available.* |
| **IgnoredInstruments** | **List&lt;string&gt;** | Required | *No description available.* |
| **ErrorFileId** | **string** | Optional | Error File ID, if one was created |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new EnrichmentResponse(
    enrichedInstruments: ,  // required
    ignoredInstruments: ,  // required
    errorFileId: "..."  // optional — Error File ID, if one was created
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EnrichmentResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

