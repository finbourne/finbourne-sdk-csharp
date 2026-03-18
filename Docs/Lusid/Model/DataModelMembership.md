# Finbourne.Sdk.Lusid.Model.DataModelMembership

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Membership** | [List&lt;Membership&gt;](Membership.md) | Required | The collection of data models this entity is a member of. |
| **CurrentModel** | [MembershipAndStatus](MembershipAndStatus.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DataModelMembership(
    membership: new List<Membership>(),  // required — The collection of data models this entity is a member of.
    currentModel: new MembershipAndStatus(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DataModelMembership>(json);
```


## Related Models

- [Membership](Membership.md) — used in `Membership`
- [MembershipAndStatus](MembershipAndStatus.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

