# Finbourne.Sdk.Lusid.Model.InstrumentEventInstructionsResponse

The collection of successfully upserted instructions, and the collection of failures for those instructions that could not be upserted
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, InstrumentEventInstruction&gt;](InstrumentEventInstruction.md) | Optional | The collection of successfully upserted instructions |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The collection of error information for instructions that could not be upserted |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentEventInstructionsResponse(
    values: new InstrumentEventInstruction(...),  // optional — The collection of successfully upserted instructions
    failed: new ErrorDetail(...)  // optional — The collection of error information for instructions that could not be upserted
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentEventInstructionsResponse>(json);
```


## Related Models

- [InstrumentEventInstruction](InstrumentEventInstruction.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

