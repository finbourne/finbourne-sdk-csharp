# Finbourne.Sdk.Lusid.Model.RecResult

An individual reconciliation result — the aggregate result for a set of core rule values within a  rec type, with its type/status, review and exception axes, rule values and item-level detail.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The system-generated identifier for the rec result. Comprises the rec definition id, the instance id, the rec type and the core rule values. |
| **RecType** | **string** | Required | The type of rec that the result belongs to (e.g. Holding). Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity. |
| **InstanceId** | [RecInstanceId](RecInstanceId.md) | Required | *No description available.* |
| **RecDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RunNumber** | **int** | Required | The run number within the instance. Increments with each re-run. |
| **RunAsAt** | **DateTimeOffset** | Required | The asAt datetime at which the run happened. |
| **DatesReconciled** | [RecDatesReconciled](RecDatesReconciled.md) | Required | *No description available.* |
| **ResultType** | **string** | Required | The type of result. Exceptions: PartialMatch, PartialCross, Break. Non-exceptions: Match, Cross. Available values: Match, Cross, PartialMatch, PartialCross, Break. |
| **ResultCardinality** | **string** | Required | The item cardinality of the result, read left to right (e.g. OneToOne, ManyToNone). Available values: OneToOne, OneToMany, ManyToOne, ManyToMany, OneToNone, ManyToNone, NoneToOne, NoneToMany, NoneToNone. |
| **ResultLifeCycle** | **string** | Required | The run-over-run change in the result, evaluated each run against the prior run. Available values: New, Unchanged, Changed, Cleared. |
| **Exception** | [RecResultException](RecResultException.md) | Optional | *No description available.* |
| **Review** | [RecResultReview](RecResultReview.md) | Required | *No description available.* |
| **CoreRules** | [List&lt;CoreRuleValues&gt;](CoreRuleValues.md) | Required | The core matching rules and the values that pin this result to its reconciled position. |
| **AggregateRules** | [List&lt;AggregateRuleValues&gt;](AggregateRuleValues.md) | Required | The aggregate matching rules and their measured values. |
| **SupplementalAttributes** | [List&lt;SupplementalAttributeValues&gt;](SupplementalAttributeValues.md) | Required | Additional attribute values carried on the result for context. Do not contribute to matching or the result id. |
| **Items** | [RecResultItemDetails](RecResultItemDetails.md) | Required | *No description available.* |
| **Comments** | [List&lt;RecUserComment&gt;](RecUserComment.md) | Required | User-authored comments attached to the result. Carried forward across runs. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties in the RecResult domain. Filterable and sortable. |
| **AssignedUser** | **string** | Optional | The LUSID user id assigned to the result. |
| **AssignedRole** | **string** | Optional | The LUSID IAM role id assigned to the result. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResult(
    id: "...",  // required — The system-generated identifier for the rec result. Comprises the rec definition id, the instance id, the rec type and the core rule values.
    recType: "...",  // required — The type of rec that the result belongs to (e.g. Holding). Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity.
    instanceId: new RecInstanceId(...),  // required
    recDefinitionId: new ResourceId(...),  // required
    runNumber: 0,  // required — The run number within the instance. Increments with each re-run.
    runAsAt: DateTimeOffset.Now,  // required — The asAt datetime at which the run happened.
    datesReconciled: new RecDatesReconciled(...),  // required
    resultType: "...",  // required — The type of result. Exceptions: PartialMatch, PartialCross, Break. Non-exceptions: Match, Cross. Available values: Match, Cross, PartialMatch, PartialCross, Break.
    resultCardinality: "...",  // required — The item cardinality of the result, read left to right (e.g. OneToOne, ManyToNone). Available values: OneToOne, OneToMany, ManyToOne, ManyToMany, OneToNone, ManyToNone, NoneToOne, NoneToMany, NoneToNone.
    resultLifeCycle: "...",  // required — The run-over-run change in the result, evaluated each run against the prior run. Available values: New, Unchanged, Changed, Cleared.
    exception: new RecResultException(...),  // optional
    review: new RecResultReview(...),  // required
    coreRules: new List<CoreRuleValues>(),  // required — The core matching rules and the values that pin this result to its reconciled position.
    aggregateRules: new List<AggregateRuleValues>(),  // required — The aggregate matching rules and their measured values.
    supplementalAttributes: new List<SupplementalAttributeValues>(),  // required — Additional attribute values carried on the result for context. Do not contribute to matching or the result id.
    items: new RecResultItemDetails(...),  // required
    comments: new List<RecUserComment>(),  // required — User-authored comments attached to the result. Carried forward across runs.
    properties: new PerpetualProperty(...),  // optional — Properties in the RecResult domain. Filterable and sortable.
    assignedUser: "...",  // optional — The LUSID user id assigned to the result.
    assignedRole: "...",  // optional — The LUSID IAM role id assigned to the result.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResult>(json);
```

- [RecInstanceId](RecInstanceId.md)
- [ResourceId](ResourceId.md)
- [RecDatesReconciled](RecDatesReconciled.md)
- [RecResultException](RecResultException.md)
- [RecResultReview](RecResultReview.md)
- [CoreRuleValues](CoreRuleValues.md) — used in `CoreRules`
- [AggregateRuleValues](AggregateRuleValues.md) — used in `AggregateRules`
- [SupplementalAttributeValues](SupplementalAttributeValues.md) — used in `SupplementalAttributes`
- [RecResultItemDetails](RecResultItemDetails.md)
- [RecUserComment](RecUserComment.md) — used in `Comments`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

