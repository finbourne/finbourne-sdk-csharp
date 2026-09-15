# Finbourne.Sdk.Lusid.Model.BucketSetShareClassDetails

Identifying detail for the share class a bucket set node is for.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LusidInstrumentId** | **string** | Optional | LUSID&#39;s internal unique instrument identifier for the share class&#39; instrument. Absent where the instrument has not been resolved. |
| **InstrumentScope** | **string** | Optional | The scope in which the share class instrument lies. Absent where the instrument has not been resolved. |
| **ShortCode** | **string** | Required | The unique code within the fund for the share class. |
| **DomCurrency** | **string** | Optional | The domestic currency declared for the share class. |
| **InstrumentActive** | **bool** | Required | Whether the share class&#39; instrument is active. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketSetShareClassDetails(
    lusidInstrumentId: "...",  // optional — LUSID&#39;s internal unique instrument identifier for the share class&#39; instrument. Absent where the instrument has not been resolved.
    instrumentScope: "...",  // optional — The scope in which the share class instrument lies. Absent where the instrument has not been resolved.
    shortCode: "...",  // required — The unique code within the fund for the share class.
    domCurrency: "...",  // optional — The domestic currency declared for the share class.
    instrumentActive: true  // required — Whether the share class&#39; instrument is active.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketSetShareClassDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

