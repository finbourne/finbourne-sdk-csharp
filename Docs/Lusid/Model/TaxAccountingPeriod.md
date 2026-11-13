# Finbourne.Sdk.Lusid.Model.TaxAccountingPeriod

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Optional | The label of the period, for example the four-digit year. |
| **Start** | **DateTimeOffset** | Optional | The first day of the period, inclusive. |
| **End** | **DateTimeOffset** | Optional | The last day of the period, inclusive. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxAccountingPeriod(
    label: "...",  // optional — The label of the period, for example the four-digit year.
    start: DateTimeOffset.Now,  // optional — The first day of the period, inclusive.
    end: DateTimeOffset.Now  // optional — The last day of the period, inclusive.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxAccountingPeriod>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

