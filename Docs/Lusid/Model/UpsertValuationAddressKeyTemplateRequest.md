# Finbourne.Sdk.Lusid.Model.UpsertValuationAddressKeyTemplateRequest

The content of a Valuation Template. An upsert replaces the display name, description and metrics.  If isDefault is not specified, the template keeps its current default flag.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the Valuation Template. |
| **Description** | **string** | Optional | A description of the Valuation Template. |
| **Metrics** | [List&lt;AggregateSpec&gt;](AggregateSpec.md) | Required | The metrics to calculate in a valuation that uses this template. Each metric is an address key, an operation and optional key options. Valuation Templates do not support returnAs. |
| **IsDefault** | **bool?** | Optional | Set to true to make this template the domain default. The previous default stops being the default. Set to false on the current default to use the system default again. If not specified, the template keeps its current value. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertValuationAddressKeyTemplateRequest(
    displayName: "...",  // required — The name of the Valuation Template.
    description: "...",  // optional — A description of the Valuation Template.
    metrics: new List<AggregateSpec>(),  // required — The metrics to calculate in a valuation that uses this template. Each metric is an address key, an operation and optional key options. Valuation Templates do not support returnAs.
    isDefault: true  // optional — Set to true to make this template the domain default. The previous default stops being the default. Set to false on the current default to use the system default again. If not specified, the template keeps its current value.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertValuationAddressKeyTemplateRequest>(json);
```

- [AggregateSpec](AggregateSpec.md) — used in `Metrics`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

