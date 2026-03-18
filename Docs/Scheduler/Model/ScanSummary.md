# Finbourne.Sdk.Scheduler.Model.ScanSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Fixable** | **int?** | Optional | The number of vulnerabilities that have a known fix |
| **Total** | **int?** | Optional | The total number of vulnerabilities |
| **Critical** | **int?** | Optional | The number of Critical severity vulnerabilities |
| **High** | **int?** | Optional | The number of High severity vulnerabilities |
| **Medium** | **int?** | Optional | The number of Medium severity vulnerabilities |
| **Low** | **int?** | Optional | The number of Low severity vulnerabilities |
| **Negligible** | **int?** | Optional | The number of Negligible severity vulnerabilities |
| **Unknown** | **int?** | Optional | The number of Unknown severity vulnerabilities |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new ScanSummary(
    fixable: 0,  // optional — The number of vulnerabilities that have a known fix
    total: 0,  // optional — The total number of vulnerabilities
    critical: 0,  // optional — The number of Critical severity vulnerabilities
    high: 0,  // optional — The number of High severity vulnerabilities
    medium: 0,  // optional — The number of Medium severity vulnerabilities
    low: 0,  // optional — The number of Low severity vulnerabilities
    negligible: 0,  // optional — The number of Negligible severity vulnerabilities
    unknown: 0  // optional — The number of Unknown severity vulnerabilities
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScanSummary>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

