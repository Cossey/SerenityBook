# Quick Filters

The Quick Filter appears above a Grid and provides options for filtering data from it.

![](/assets/QuickFilter.png)

There are two ways to create Quick Filters

1. via the `QuickFilterAttribute`.
2. via TypeScript code.

### Creating Quick Filters

##### Using Attributes

You can create Quick Filter by applying the `[QuickFilter]` attribute to a Property in a `Column.cs` file. Editors applied to the Column, via the Serenity Row Class will be used for the Filter.

```csharp
[ColumnsScript("ExampleColumns")]
[BasedOnRow(typeof(Entities.ExampleRow))]
public class ExampleColumns
{
    public String NonQuickFilteredField { get; set; }

    [QuickFilter]
    public String QuickFilteredField { get; set; }

    [QuickFilter]
    public String AnotherQuickFilteredField { get; set; }
}
```

##### Using Code

To create a Quick Filter via Code you override the `getQuickFilters()` function in the `Grid.ts` file and return an array of Filters to create.

```typescript
protected getQuickFilters(): Serenity.QuickFilter<Serenity.Widget<any>, any>[] {
    //Gets the Filters defined in the Columns or in parent grids.
    let filters = super.getQuickFilters();

    //Insert a new checkbox filter for seeing if the column DeletedOn (date) is not Null
    //Show or hide deleted items option
    filters.push({
        field: EntityRow.Fields.DeletedOn,
        type: Serenity.BooleanEditor,
        title: "Show Deleted",
        handler: h => {
            h.active = !!h.value;
            if (h.active) {
                h.request.Criteria = Serenity.Criteria.and(h.request.Criteria,
                ['is not null', [EntityRow.Fields.DeletedOn]]);
            } else {
                h.request.Criteria = Serenity.Criteria.and(h.request.Criteria,            
                ['is null', [EntityRow.Fields.DeletedOn]]);                
            }
        }
    });

    return filters;
}
```

### Quick Filter Options

The quick filter options are configured via the `QuickFilterOption` attribute.

##### Options

| Option | Type | Description |
| :--- | :--- | :--- |
| Multiple | boolean | Allows the Quick Filter to have multiple values. |
| CascadeField | String |  |
| CascadeFrom | String |  |
| CascadeValue | Any |  |
| FilterField | String | The ID, Name or LookupInclude field to filter the Lookup by. |
| FilterValue | Any | The value of the Filter field to filter the Lookup by. |



