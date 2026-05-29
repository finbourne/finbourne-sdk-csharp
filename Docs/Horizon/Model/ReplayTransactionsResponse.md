# Finbourne.Sdk.Horizon.Model.ReplayTransactionsResponse

Response from a replay transactions operation containing the CSV output.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BatchReferenceId** | **string** | Required | *No description available.* |
| **Mode** | **string** | Required | *No description available.* |
| **TransactionCount** | **int** | Required | *No description available.* |
| **CsvOutput** | **string** | Required | *No description available.* |
| **Message** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ReplayTransactionsResponse(
    batchReferenceId: "...",  // required
    mode: "...",  // required
    transactionCount: 0,  // required
    csvOutput: "...",  // required
    message: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReplayTransactionsResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

