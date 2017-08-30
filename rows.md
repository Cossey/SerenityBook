# Data Rows

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



