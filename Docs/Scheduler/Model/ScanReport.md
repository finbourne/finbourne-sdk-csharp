# Finbourne.Sdk.Scheduler.Model.ScanReport

Represents the details of a security scan of an image
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Severity** | **string** | Optional | The overall severity. For example : \&quot;High\&quot; or \&quot;None\&quot; |
| **Status** | **string** | Optional | The status of the report |
| **StartTime** | **DateTimeOffset?** | Optional | The start time of the scanning process |
| **EndTime** | **DateTimeOffset?** | Optional | The end time of the scanning process |
| **ScanDuration** | **int?** | Optional | The duration of the scan in seconds |
| **Summary** | [ScanSummary](ScanSummary.md) | Optional | *No description available.* |
| **Vulnerabilities** | [List&lt;Vulnerability&gt;](Vulnerability.md) | Optional | List of Finbourne.Scheduler.WebApi.Dtos.Images.Vulnerability |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new ScanReport(
    severity: "...",  // optional — The overall severity. For example : \&quot;High\&quot; or \&quot;None\&quot;
    status: "...",  // optional — The status of the report
    startTime: DateTimeOffset.Now,  // optional — The start time of the scanning process
    endTime: DateTimeOffset.Now,  // optional — The end time of the scanning process
    scanDuration: 0,  // optional — The duration of the scan in seconds
    summary: new ScanSummary(...),  // optional
    vulnerabilities: new List<Vulnerability>()  // optional — List of Finbourne.Scheduler.WebApi.Dtos.Images.Vulnerability
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScanReport>(json);
```

- [ScanSummary](ScanSummary.md)
- [Vulnerability](Vulnerability.md) — used in `Vulnerabilities`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

