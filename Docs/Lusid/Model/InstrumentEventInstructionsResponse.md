# Finbourne.Sdk.Lusid.Model.InstrumentEventInstructionsResponse

The collection of successfully upserted instructions, the collection of those staged pending approval, and the collection of failures for those instructions that could not be upserted
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, InstrumentEventInstruction&gt;](InstrumentEventInstruction.md) | Optional | The collection of successfully upserted instructions |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The collection of error information for instructions that could not be upserted |
| **Staged** | [Dictionary&lt;string, InstrumentEventInstruction&gt;](InstrumentEventInstruction.md) | Optional | The instructions that have been staged pending approval. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentEventInstructionsResponse(
    values: new InstrumentEventInstruction(...),  // optional — The collection of successfully upserted instructions
    failed: new ErrorDetail(...),  // optional — The collection of error information for instructions that could not be upserted
    staged: new InstrumentEventInstruction(...)  // optional — The instructions that have been staged pending approval.
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
- [InstrumentEventInstruction](InstrumentEventInstruction.md) — used in `Staged`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

