# Finbourne.Sdk.Horizon.Model.TpfTransactionSearchRequest

Request body for the POST transaction-search endpoint. Multiple values in TransactionIds and InstrumentIdentifiers are OR'd within each filter; both filters together are AND'd.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionIds** | **List&lt;string&gt;** | Optional | One or more LUSID transaction IDs to search for (max 50). Values are OR&#39;d. |
| **InstrumentIdentifiers** | **List&lt;string&gt;** | Optional | One or more instrument identifiers in any supported format (ISIN, CUSIP, LUID, etc.) to search for (max 50). Values are OR&#39;d. |
| **InstanceId** | **string** | Optional | Instance ID to filter by. Omit or leave null to search all instances the caller has access to. |
| **From** | **DateTimeOffset?** | Optional | Start of the date range (inclusive). Defaults to 30 days ago if neither From nor To is provided. |
| **To** | **DateTimeOffset?** | Optional | End of the date range (inclusive). Defaults to now if not provided. |
| **Limit** | **int?** | Optional | Maximum number of results to return per page. |
| **Page** | **string** | Optional | Pagination token from a previous response NextPage or PreviousPage. Omit for the first page. |
| **Status** | **string** | Optional | Publication status to filter by. Valid values: Sent, Skipped, Failed. Optional. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfTransactionSearchRequest(
    transactionIds: ,  // optional — One or more LUSID transaction IDs to search for (max 50). Values are OR&#39;d.
    instrumentIdentifiers: ,  // optional — One or more instrument identifiers in any supported format (ISIN, CUSIP, LUID, etc.) to search for (max 50). Values are OR&#39;d.
    instanceId: "...",  // optional — Instance ID to filter by. Omit or leave null to search all instances the caller has access to.
    from: DateTimeOffset.Now,  // optional — Start of the date range (inclusive). Defaults to 30 days ago if neither From nor To is provided.
    to: DateTimeOffset.Now,  // optional — End of the date range (inclusive). Defaults to now if not provided.
    limit: 0,  // optional — Maximum number of results to return per page.
    page: "...",  // optional — Pagination token from a previous response NextPage or PreviousPage. Omit for the first page.
    status: "..."  // optional — Publication status to filter by. Valid values: Sent, Skipped, Failed. Optional.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TpfTransactionSearchRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

