# Finbourne.Sdk.Lusid.Model.AllocationMapParticipants

Who takes part in the allocations of an Allocation Map: the default rule that finds the participant set, and the  exceptions that exclude particular investor records or fix their share.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Rule** | **string** | Optional | How the default participant set is found. AllCommittedToMembers takes every investor record committed to any of the funds in memberIds; ExplicitList takes exactly the investor records in explicitInvestorRecordIds. Available values: AllCommittedToMembers, ExplicitList. |
| **MemberIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | Under the AllCommittedToMembers rule, the member funds whose committed investor records participate, as scope and code. At least one is required under that rule. |
| **ExplicitInvestorRecordIds** | **List&lt;string&gt;** | Optional | Under the ExplicitList rule, the investor records that participate. At least one is required under that rule. |
| **Exceptions** | [List&lt;AllocationMapException&gt;](AllocationMapException.md) | Optional | Departures from the default participation for particular investor records. Each names the investor record, what happens to it, and why. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapParticipants(
    rule: "...",  // optional — How the default participant set is found. AllCommittedToMembers takes every investor record committed to any of the funds in memberIds; ExplicitList takes exactly the investor records in explicitInvestorRecordIds. Available values: AllCommittedToMembers, ExplicitList.
    memberIds: new List<ResourceId>(),  // optional — Under the AllCommittedToMembers rule, the member funds whose committed investor records participate, as scope and code. At least one is required under that rule.
    explicitInvestorRecordIds: ,  // optional — Under the ExplicitList rule, the investor records that participate. At least one is required under that rule.
    exceptions: new List<AllocationMapException>()  // optional — Departures from the default participation for particular investor records. Each names the investor record, what happens to it, and why.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapParticipants>(json);
```

- [ResourceId](ResourceId.md) — used in `MemberIds`
- [AllocationMapException](AllocationMapException.md) — used in `Exceptions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

