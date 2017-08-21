To create a Quick Filter via Code you create the `getQuickFilters()` function and return the list of Filters to want to create.

```js
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



