# Finbourne.Sdk.Horizon.Model.RunFileResponse

One delivery of a file to one destination within a run, keyed by FileUuid. A file sent to two destinations appears as two rows, so Destinations always holds exactly one element.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FileName** | **string** | Required | *No description available.* |
| **GeneratedAt** | **DateTimeOffset** | Required | When the file was built, or when the attempt failed before a file was built. |
| **RowCount** | **int** | Required | *No description available.* |
| **FileHash** | **string** | Required | *No description available.* |
| **Encrypted** | **bool** | Required | *No description available.* |
| **Destinations** | [List&lt;FileDestinationResponse&gt;](FileDestinationResponse.md) | Required | *No description available.* |
| **TransactionIds** | **List&lt;string&gt;** | Required | *No description available.* |
| **FileUuid** | **Guid** | Required | *No description available.* |
| **FailedTransactionIds** | **List&lt;string&gt;** | Required | *No description available.* |
| **CanResend** | **bool** | Required | Whether the data the file is rebuilt from is still retained, so a resend can be requested. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new RunFileResponse(
    fileName: "...",  // required
    generatedAt: DateTimeOffset.Now,  // required — When the file was built, or when the attempt failed before a file was built.
    rowCount: 0,  // required
    fileHash: "...",  // required
    encrypted: true,  // required
    destinations: new List<FileDestinationResponse>(),  // required
    transactionIds: ,  // required
    fileUuid: "...",  // required
    failedTransactionIds: ,  // required
    canResend: true  // required — Whether the data the file is rebuilt from is still retained, so a resend can be requested.
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

