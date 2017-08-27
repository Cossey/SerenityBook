# Requiring a Quick Filter Value

If you require a Quick Filter value for a field then you can follow some approaches below.

### Lookup Editors

##### Disable the Ability to clear the Lookup Value

Set the Select2 option `allowClear` to false by using the Attribute `[QuickFilterOption("AllowClear", false)]` on a column property.

##### Configure a default value

You can set a default value to be selected in the Lookup Editor. This can be done via a Serenity Grid TypeScript File in the `getQuickFilters()` or `createQuickFilters()` functions.

```typescript
protected createQuickFilters(): void {
    //Create filters from base class
    super.createQuickFilters();

    // get a reference to order row field names
    let fld = Northwind.OrderRow.Fields;

    // find a quick filter widget by its field name
    this.findQuickFilter(Serenity.EnumEditor, fld.ShippingState).value = Northwind.OrderShippingState.NotShipped.toString();
}
```

##### Make an Empty Lookup Editor display no Grid Data

To make a Grid empty when you clear a required Quick Filter you can

