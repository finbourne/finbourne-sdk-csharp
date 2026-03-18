# Finbourne.Sdk.Luminesce.Model.JoinedTableDesign

Treatment of a joined-to-table a QueryDesign
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **JoinedTableName** | **string** | Required | Name of the table on the right side of the join |
| **JoinedTableAlias** | **string** | Required | Alias for the table on the right side of the join |
| **LeftTableAlias** | **string** | Required | Alias for the table on the left side of the join |
| **JoinType** | **DesignJoinType** | Required | *No description available.* |
| **OnClauseTerms** | [List&lt;OnClauseTermDesign&gt;](OnClauseTermDesign.md) | Required | Filter clauses to apply to this join in the on clause |
| **RightTableAvailableFields** | [List&lt;AvailableField&gt;](AvailableField.md) | Optional | Fields that are known to be available for design when parsing SQL, of the right hand table |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new JoinedTableDesign(
    joinedTableName: "...",  // required — Name of the table on the right side of the join
    joinedTableAlias: "...",  // required — Alias for the table on the right side of the join
    leftTableAlias: "...",  // required — Alias for the table on the left side of the join
    joinType: ,  // required
    onClauseTerms: new List<OnClauseTermDesign>(),  // required — Filter clauses to apply to this join in the on clause
    rightTableAvailableFields: new List<AvailableField>()  // optional — Fields that are known to be available for design when parsing SQL, of the right hand table
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<JoinedTableDesign>(json);
```

- [OnClauseTermDesign](OnClauseTermDesign.md) — used in `OnClauseTerms`
- [AvailableField](AvailableField.md) — used in `RightTableAvailableFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

