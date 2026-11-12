# Finbourne.Sdk.Lusid.Model.ReturnZeroPvOptions

Options to indicate which errors to ignore when performing valuation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentMatured** | **bool** | Optional | Deprecated: use pricing.options.maturedInstrumentValuation, where true corresponds to  \&quot;ZeroPv\&quot; and false to \&quot;Fail\&quot;. Indicates whether attempting to value an instrument after  its maturity date should produce a failure (false) or a zero PV (true).  Ignored when maturedInstrumentValuation is set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReturnZeroPvOptions(
    instrumentMatured: true  // optional — Deprecated: use pricing.options.maturedInstrumentValuation, where true corresponds to  \&quot;ZeroPv\&quot; and false to \&quot;Fail\&quot;. Indicates whether attempting to value an instrument after  its maturity date should produce a failure (false) or a zero PV (true).  Ignored when maturedInstrumentValuation is set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReturnZeroPvOptions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

