# Finbourne.Sdk.Horizon.Model.OnboardInstrumentResponse

Simplified structure converted from the LUSID UpsertInstrumentReponse
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | **List&lt;string&gt;** | Required | The instruments which have been successfully updated or created. |
| **Failed** | **Dictionary&lt;string, string&gt;** | Required | The instruments that could not be updated or created or were left unchanged without error along with a reason for their failure. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new OnboardInstrumentResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: ,  // required — The instruments which have been successfully updated or created.
    failed:   // required — The instruments that could not be updated or created or were left unchanged without error along with a reason for their failure.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OnboardInstrumentResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

