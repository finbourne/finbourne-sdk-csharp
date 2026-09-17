# Finbourne.Sdk.Lusid.Model.VirtualTransactionOverridesResponse

The overrides and suppressions affecting a single instrument event in the requested portfolio. A derived  portfolio is affected by its own record and by every record held by an ancestor, so one record per  holding portfolio is returned, nearest first.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **InstrumentEventId** | **string** | Required | The identifier of the instrument event whose overrides and suppressions are returned. |
| **Records** | [List&lt;VirtualTransactionOverrideRecord&gt;](VirtualTransactionOverrideRecord.md) | Optional | The override and suppression records affecting the requested portfolio for this instrument event, nearest first. A derived portfolio is affected by its own record and by every record held by an ancestor. |
| **Live** | **List&lt;string&gt;** | Optional | The virtual transaction ids the event currently generates in the requested portfolio that no returned record targets, and so keep generating unmodified. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VirtualTransactionOverridesResponse(
    varVersion: new ModelVersion(...),  // required
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    instrumentEventId: "...",  // required — The identifier of the instrument event whose overrides and suppressions are returned.
    records: new List<VirtualTransactionOverrideRecord>(),  // optional — The override and suppression records affecting the requested portfolio for this instrument event, nearest first. A derived portfolio is affected by its own record and by every record held by an ancestor.
    live: ,  // optional — The virtual transaction ids the event currently generates in the requested portfolio that no returned record targets, and so keep generating unmodified.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VirtualTransactionOverridesResponse>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [VirtualTransactionOverrideRecord](VirtualTransactionOverrideRecord.md) — used in `Records`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

