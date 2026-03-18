# Finbourne.Sdk.Lusid.Model.LusidUniqueId

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type for the LUSID unique id, this will depend on the type of entity found, for instance &#39;Instrument&#39; would have a value of &#39;LusidInstrumentId&#39; |
| **Value** | **string** | Required | The value for the LUSID unique id |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LusidUniqueId(
    type: "...",  // required — The type for the LUSID unique id, this will depend on the type of entity found, for instance &#39;Instrument&#39; would have a value of &#39;LusidInstrumentId&#39;
    value: "..."  // required — The value for the LUSID unique id
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidUniqueId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

