# Finbourne.Sdk.Lusid.Model.TransactionDiagnostics

Represents a set of diagnostics per transaction, where applicable.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionDisplayName** | **string** | Required | *No description available.* |
| **ErrorDetails** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionDiagnostics(
    transactionDisplayName: "...",  // required
    errorDetails:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionDiagnostics>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

