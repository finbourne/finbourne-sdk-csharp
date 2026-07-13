# Finbourne.Sdk.Horizon.Model.TransactionPayload

record containing the payload for a single transaction. Columns is compiled once from the TPF instance configuration and is identical across every item in the paginated result.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | *No description available.* |
| **Columns** | **List&lt;string&gt;** | Required | *No description available.* |
| **Values** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **RawCsvRow** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TransactionPayload(
    transactionId: "...",  // required
    columns: ,  // required
    values: ,  // required
    rawCsvRow: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionPayload>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

