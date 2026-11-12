# Finbourne.Sdk.Horizon.Model.TpfTransactionSearchRequest

Request body for the POST transaction-search endpoint. Multiple values in TransactionIds and InstrumentIdentifiers are OR'd within each filter; both filters together are AND'd.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionIds** | **List&lt;string&gt;** | Optional | One or more LUSID transaction IDs to search for (max 50, each 1 to 256 characters). Values are OR&#39;d. An empty ID, or one with leading or trailing whitespace, is rejected with 400, as LUSID never stores one. |
| **InstrumentIdentifiers** | **List&lt;string&gt;** | Optional | One or more instrument identifiers to search for (max 50). Values are OR&#39;d. Accepts LusidInstrumentId, Isin, Figi, Ticker, Cusip, Sedol or ClientInternal values. Every value is matched exactly against the stored instrument id; non-LUID values are also resolved against LUSID instruments in the default scope, whose own matching rules (including case) apply. |
| **InstanceId** | **string** | Optional | Instance ID to filter by. Omit or leave null to search all instances the caller has access to. |
| **From** | **DateTimeOffset?** | Optional | Start of the date range (inclusive). Defaults to 30 days ago if neither From nor To is provided. |
| **To** | **DateTimeOffset?** | Optional | End of the date range (inclusive). Defaults to now if not provided. |
| **Limit** | **int?** | Optional | Maximum number of results to return per page. |
| **Page** | **string** | Optional | Pagination token from a previous response NextPage or PreviousPage. Omit for the first page. |
| **Status** | **string** | Optional | Publication statuses to filter by: one or more of Sent, Skipped, Failed separated by &#39;|&#39;, in any case, for example \&quot;Failed|Skipped\&quot;. A value outside that set is rejected. Optional. |
| **Filter** | **string** | Optional | Filter expression to apply to the results, in the format \&quot;property operator value\&quot; (e.g., eq, ne, gt, lt), combined with \&quot;and\&quot;/\&quot;or\&quot; as needed. Filterable properties are transactionId, instanceName, runStartTime, instrumentName, instrumentType, instrumentId, tradeDate, settlementDate, skipReason, failureReason, failureStage, fileName, sentAt, portfolioScope, portfolioCode, runId and eventType (New, Amended, Cancelled, ...). PublicationStatus is not filterable here — use the Status body parameter instead. Dates are quoted ISO-8601. Destinations is not filterable. Comparing a field with null is rejected. Must remain the same across pages — the page token includes a hash of both filter and sortBy. |
| **SortBy** | **List&lt;string&gt;** | Optional | Up to two sortable fields, each optionally suffixed \&quot; ASC\&quot; or \&quot; DESC\&quot;. Sortable fields: transactionId, instanceName, runStartTime, instrumentName, instrumentType, instrumentId, tradeDate, settlementDate, eventType, skipReason, failureReason, failureStage, fileName, sentAt, portfolioScope, portfolioCode, runId. Deterministic tiebreakers are appended automatically: RunStartTime DESC, TransactionId ASC, BatchUuid ASC, FileName ASC. Must remain the same across pages — the page token includes a hash of both filter and sortBy. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfTransactionSearchRequest(
    transactionIds: ,  // optional — One or more LUSID transaction IDs to search for (max 50, each 1 to 256 characters). Values are OR&#39;d. An empty ID, or one with leading or trailing whitespace, is rejected with 400, as LUSID never stores one.
    instrumentIdentifiers: ,  // optional — One or more instrument identifiers to search for (max 50). Values are OR&#39;d. Accepts LusidInstrumentId, Isin, Figi, Ticker, Cusip, Sedol or ClientInternal values. Every value is matched exactly against the stored instrument id; non-LUID values are also resolved against LUSID instruments in the default scope, whose own matching rules (including case) apply.
    instanceId: "...",  // optional — Instance ID to filter by. Omit or leave null to search all instances the caller has access to.
    from: DateTimeOffset.Now,  // optional — Start of the date range (inclusive). Defaults to 30 days ago if neither From nor To is provided.
    to: DateTimeOffset.Now,  // optional — End of the date range (inclusive). Defaults to now if not provided.
    limit: 0,  // optional — Maximum number of results to return per page.
    page: "...",  // optional — Pagination token from a previous response NextPage or PreviousPage. Omit for the first page.
    status: "...",  // optional — Publication statuses to filter by: one or more of Sent, Skipped, Failed separated by &#39;|&#39;, in any case, for example \&quot;Failed|Skipped\&quot;. A value outside that set is rejected. Optional.
    filter: "...",  // optional — Filter expression to apply to the results, in the format \&quot;property operator value\&quot; (e.g., eq, ne, gt, lt), combined with \&quot;and\&quot;/\&quot;or\&quot; as needed. Filterable properties are transactionId, instanceName, runStartTime, instrumentName, instrumentType, instrumentId, tradeDate, settlementDate, skipReason, failureReason, failureStage, fileName, sentAt, portfolioScope, portfolioCode, runId and eventType (New, Amended, Cancelled, ...). PublicationStatus is not filterable here — use the Status body parameter instead. Dates are quoted ISO-8601. Destinations is not filterable. Comparing a field with null is rejected. Must remain the same across pages — the page token includes a hash of both filter and sortBy.
    sortBy:   // optional — Up to two sortable fields, each optionally suffixed \&quot; ASC\&quot; or \&quot; DESC\&quot;. Sortable fields: transactionId, instanceName, runStartTime, instrumentName, instrumentType, instrumentId, tradeDate, settlementDate, eventType, skipReason, failureReason, failureStage, fileName, sentAt, portfolioScope, portfolioCode, runId. Deterministic tiebreakers are appended automatically: RunStartTime DESC, TransactionId ASC, BatchUuid ASC, FileName ASC. Must remain the same across pages — the page token includes a hash of both filter and sortBy.
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

