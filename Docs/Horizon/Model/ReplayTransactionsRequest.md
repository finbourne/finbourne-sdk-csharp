# Finbourne.Sdk.Horizon.Model.ReplayTransactionsRequest

Request to replay one or more transactions through a TPF instance. The instance ID is specified in the route path.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionIds** | **List&lt;string&gt;** | Required | List of transaction IDs to replay. |
| **Mode** | **string** | Required | Replay mode - DryRun (preview only) or Committed (real send). |
| **Destinations** | **List&lt;string&gt;** | Optional | Target destinations for Committed mode. Required for Committed, forbidden for DryRun. Valid values: Drive, Sftp, S3, Local |
| **Options** | [ReplayOptions](ReplayOptions.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ReplayTransactionsRequest(
    transactionIds: ,  // required — List of transaction IDs to replay.
    mode: "...",  // required — Replay mode - DryRun (preview only) or Committed (real send).
    destinations: ,  // optional — Target destinations for Committed mode. Required for Committed, forbidden for DryRun. Valid values: Drive, Sftp, S3, Local
    options: new ReplayOptions(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReplayTransactionsRequest>(json);
```

- [ReplayOptions](ReplayOptions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

