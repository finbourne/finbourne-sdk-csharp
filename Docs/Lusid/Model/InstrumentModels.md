# Finbourne.Sdk.Lusid.Model.InstrumentModels

Supported pricing models for an instrument.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentId** | **string** | Optional | The unique LUSID Instrument Identifier (LUID) of the instrument. |
| **SupportedModels** | **List&lt;string&gt;** | Optional | The pricing models supported by the instrument e.g. &#39;Discounting&#39;. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentModels(
    instrumentId: "...",  // optional — The unique LUSID Instrument Identifier (LUID) of the instrument.
    supportedModels: ,  // optional — The pricing models supported by the instrument e.g. &#39;Discounting&#39;.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentModels>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

