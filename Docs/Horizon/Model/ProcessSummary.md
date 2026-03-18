# Finbourne.Sdk.Horizon.Model.ProcessSummary

Completed event details
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EndTime** | **DateTimeOffset?** | Optional | *No description available.* |
| **Category** | **string** | Optional | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **Message** | **string** | Required | *No description available.* |
| **Rows** | [RowDetails](RowDetails.md) | Required | *No description available.* |
| **FileDetails** | [List&lt;FileDetails&gt;](FileDetails.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ProcessSummary(
    endTime: DateTimeOffset.Now,  // optional
    category: "...",  // optional
    status: "...",  // required
    message: "...",  // required
    rows: new RowDetails(...),  // required
    fileDetails: new List<FileDetails>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessSummary>(json);
```

- [RowDetails](RowDetails.md)
- [FileDetails](FileDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

