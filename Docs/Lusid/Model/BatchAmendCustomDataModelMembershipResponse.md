# Finbourne.Sdk.Lusid.Model.BatchAmendCustomDataModelMembershipResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, MembershipAmendmentResponse&gt;](MembershipAmendmentResponse.md) | Optional | *No description available.* |
| **Staged** | [Dictionary&lt;string, MembershipAmendmentResponse&gt;](MembershipAmendmentResponse.md) | Optional | *No description available.* |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | *No description available.* |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchAmendCustomDataModelMembershipResponse(
    values: new MembershipAmendmentResponse(...),  // optional
    staged: new MembershipAmendmentResponse(...),  // optional
    failed: new ErrorDetail(...),  // optional
    metadata:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchAmendCustomDataModelMembershipResponse>(json);
```


## Related Models

- [MembershipAmendmentResponse](MembershipAmendmentResponse.md)
- [MembershipAmendmentResponse](MembershipAmendmentResponse.md)
- [ErrorDetail](ErrorDetail.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

