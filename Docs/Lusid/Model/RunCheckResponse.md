# Finbourne.Sdk.Lusid.Model.RunCheckResponse

Response containing the results of running data quality checks
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DataQualityCheckResults** | [List&lt;DataQualityCheckResult&gt;](DataQualityCheckResult.md) | Optional | Collection of data quality check results |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RunCheckResponse(
    dataQualityCheckResults: new List<DataQualityCheckResult>()  // optional — Collection of data quality check results
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunCheckResponse>(json);
```


## Related Models

- [DataQualityCheckResult](DataQualityCheckResult.md) — used in `DataQualityCheckResults`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

