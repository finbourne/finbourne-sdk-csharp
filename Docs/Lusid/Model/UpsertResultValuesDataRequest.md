# Finbourne.Sdk.Lusid.Model.UpsertResultValuesDataRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DocumentId** | [StructuredResultDataId](StructuredResultDataId.md) | Required | *No description available.* |
| **Key** | **Dictionary&lt;string, string&gt;** | Optional | The structured unit result data key. |
| **DataAddress** | **string** | Optional | The address of the piece of unit result data |
| **ResultValue** | [ResultValue](ResultValue.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertResultValuesDataRequest(
    documentId: new StructuredResultDataId(...),  // required
    key: ,  // optional — The structured unit result data key.
    dataAddress: "...",  // optional — The address of the piece of unit result data
    resultValue: new ResultValue(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertResultValuesDataRequest>(json);
```


## Related Models

- [StructuredResultDataId](StructuredResultDataId.md)
- [ResultValue](ResultValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

