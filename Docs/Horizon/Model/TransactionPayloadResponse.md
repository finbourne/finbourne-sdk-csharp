# Finbourne.Sdk.Horizon.Model.TransactionPayloadResponse

record containing details of a transaction payload.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Columns** | **List&lt;string&gt;** | Required | *No description available.* |
| **Values** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **RawCsvRow** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TransactionPayloadResponse(
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
var instance = JsonConvert.DeserializeObject<TransactionPayloadResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

