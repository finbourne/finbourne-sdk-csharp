# Finbourne.Sdk.Lusid.Model.UpsertVirtualTransactionOverrideResponse

The result of upserting overrides and suppressions of virtual transactions for a single instrument event.  Returns the record as it was persisted and the new version of the record. Whether each entry currently  applies, and which virtual transactions the event still generates unmodified.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Contains warnings related to unresolved instruments, non-existent transaction types, sub-holding key mismatches, or closed accounting periods for the override transactions. |
| **InstrumentEventId** | **string** | Required | The identifier of the instrument event that was overridden. |
| **Overrides** | **Dictionary&lt;string, List&lt;StoredOverrideDefinition&gt;&gt;** | Optional | The replacement transactions persisted for the instrument event, keyed by the virtual transaction id being overridden. |
| **Suppressions** | **List&lt;string&gt;** | Optional | The virtual transaction ids suppressed for the instrument event. |
| **CancelActive** | **bool?** | Optional | True when an active event-level Cancel instruction also exists for this instrument event, taking precedence over the entries in this record. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertVirtualTransactionOverrideResponse(
    varVersion: new ModelVersion(...),  // required
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    metadata: ,  // optional — Contains warnings related to unresolved instruments, non-existent transaction types, sub-holding key mismatches, or closed accounting periods for the override transactions.
    instrumentEventId: "...",  // required — The identifier of the instrument event that was overridden.
    overrides: ,  // optional — The replacement transactions persisted for the instrument event, keyed by the virtual transaction id being overridden.
    suppressions: ,  // optional — The virtual transaction ids suppressed for the instrument event.
    cancelActive: true,  // optional — True when an active event-level Cancel instruction also exists for this instrument event, taking precedence over the entries in this record.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertVirtualTransactionOverrideResponse>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

