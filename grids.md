# Grids

Grids are configured via the `Grid.ts` files whilst `Column.cs` files contain column information for the grid and the `Dialog.ts` files contain the dialog used for editing grid data. On the front end, Serenity uses the SlickGrid component.

## Features

#### Row Grouping

Rows are grouped client side in the browser and are set in `Grid.ts` files. You must first register the grouping plugin in `createSlickGrid` function and then you can pass your grouping configuration as an array of `Slick.GroupInfo<EntityRow>` to the `view.setGrouping` function.

##### Example

```typescript
//Register the grouping plugin
protected createSlickGrid() {
    var grid = super.createSlickGrid();

    grid.registerPlugin(new Slick.Data.GroupItemMetadataProvider());

    return grid;
}

protected getButtons(): Serenity.ToolButton[] {
    var buttons = super.getButtons();
    buttons.push({
        title: 'Group by FirstName',
        cssClass: 'group-by-firstname-button',
        onClick: () => {
            this.view.setGrouping([
                {
                    formatter: x => (typeof x.value !== 'undefined'? x.value : 'Untitled'),
                    getter: 'FirstName'
                }
            ]);
        }
    });    
}
```

> The `formatter` item above sets the name of the group to `"Untitled"` when it detects undefined values \(otherwise it will display `"undefined"`\).

##### Grouping object properties

| Name | Type | Description |
| :--- | :--- | :--- |
| getter | String | The name of the field to group by. |
| formatter | String | The formatting of the display text in the group rows. |



