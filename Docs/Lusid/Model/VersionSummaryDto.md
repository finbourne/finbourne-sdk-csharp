# Finbourne.Sdk.Lusid.Model.VersionSummaryDto

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApiVersion** | **string** | Optional | *No description available.* |
| **BuildVersion** | **string** | Optional | *No description available.* |
| **ExcelVersion** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VersionSummaryDto(
    apiVersion: "...",  // optional
    buildVersion: "...",  // optional
    excelVersion: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VersionSummaryDto>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

