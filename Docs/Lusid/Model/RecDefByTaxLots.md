# Finbourne.Sdk.Lusid.Model.RecDefByTaxLots

Per-side tax-lot granularity for a Holding entry of a rec definition's rulesets.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **bool?** | Optional | Whether the left side splits holdings by tax lot. Must be omitted when the left side is relational, and reads as null there. |
| **Right** | **bool?** | Optional | Whether the right side splits holdings by tax lot. Must be omitted when the right side is relational, and reads as null there. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDefByTaxLots(
    left: true,  // optional — Whether the left side splits holdings by tax lot. Must be omitted when the left side is relational, and reads as null there.
    right: true  // optional — Whether the right side splits holdings by tax lot. Must be omitted when the right side is relational, and reads as null there.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDefByTaxLots>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

