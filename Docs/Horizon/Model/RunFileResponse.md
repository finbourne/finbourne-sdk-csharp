# Finbourne.Sdk.Horizon.Model.RunFileResponse

record containing details of a single file for a run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FileName** | **string** | Required | *No description available.* |
| **GeneratedAt** | **DateTimeOffset** | Required | *No description available.* |
| **RowCount** | **int** | Required | *No description available.* |
| **FileHash** | **string** | Required | *No description available.* |
| **Encrypted** | **bool** | Required | *No description available.* |
| **Destinations** | [List&lt;FileDestinationResponse&gt;](FileDestinationResponse.md) | Required | *No description available.* |
| **TransactionIds** | **List&lt;Guid&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new RunFileResponse(
    fileName: "...",  // required
    generatedAt: DateTimeOffset.Now,  // required
    rowCount: 0,  // required
    fileHash: "...",  // required
    encrypted: true,  // required
    destinations: new List<FileDestinationResponse>(),  // required
    transactionIds:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunFileResponse>(json);
```

- [FileDestinationResponse](FileDestinationResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

