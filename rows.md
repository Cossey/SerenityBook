# Data Rows

## Attributes

| Attribute | Type | Info |
| :--- | :--- | :--- |
| ConnectionKey | String | The Name of the ConnectionKey configured in the appsettings.json file. |
| TableName | String | The database table name. |
| DisplayName | String | The display name of the data. |
| InstanceName | String | The singular reference name of the item. |
| LookupScript | String | Sets the row up as a lookup for drop down fields. |

## Security

You can apply permissions down to the field level in a `Row.cs` file.

```csharp
[DisplayName("Cost Price")]
[ReadPermission(PermissionKeys.CostPrice)]
public Decimal? CostPrice
{
  get { return Field.CostPrice[this]; }
  set { Fields.CostPrice[this] = value; }
}
```

> By default if a user does not have a `ReadPermission` then they will also not have the `ModifyPermission`.



