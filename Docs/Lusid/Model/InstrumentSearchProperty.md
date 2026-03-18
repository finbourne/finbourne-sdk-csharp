# Finbourne.Sdk.Lusid.Model.InstrumentSearchProperty

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The property key of instrument property to search for. This will be from the &#39;Instrument&#39; domain and will take the format {domain}/{scope}/{code} e.g. &#39;Instrument/system/Isin&#39; or &#39;Instrument/MyScope/AssetClass&#39;. |
| **Value** | **string** | Required | The value of the property e.g. &#39;US0378331005&#39; or &#39;Equity&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentSearchProperty(
    key: "...",  // required — The property key of instrument property to search for. This will be from the &#39;Instrument&#39; domain and will take the format {domain}/{scope}/{code} e.g. &#39;Instrument/system/Isin&#39; or &#39;Instrument/MyScope/AssetClass&#39;.
    value: "..."  // required — The value of the property e.g. &#39;US0378331005&#39; or &#39;Equity&#39;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentSearchProperty>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

