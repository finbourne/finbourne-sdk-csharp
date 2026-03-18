# Finbourne.Sdk.Horizon.Model.Identifiers

A list of lusid instrument ids
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LusidInstrumentIds** | **List&lt;string&gt;** | Required | The collection of LUSID instrument identifiers |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new Identifiers(
    lusidInstrumentIds:   // required — The collection of LUSID instrument identifiers
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Identifiers>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

