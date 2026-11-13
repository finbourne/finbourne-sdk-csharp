# Finbourne.Sdk.Lusid.Model.TaxReconciliationBridgeRow

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Optional | The label of the period, for example the four-digit year. |
| **Amount** | **decimal** | Optional | The amount, in pounds. |
| **RunningTotal** | **decimal** | Optional | The running total after this step of the bridge. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReconciliationBridgeRow(
    label: "...",  // optional — The label of the period, for example the four-digit year.
    amount: 0.0d,  // optional — The amount, in pounds.
    runningTotal: 0.0d  // optional — The running total after this step of the bridge.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReconciliationBridgeRow>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

