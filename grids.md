# Grids

Grids are configured via the `Grid.ts` files whilst `Column.cs` files contain column information for the grid and the `Dialog.ts` files contain the dialog used for editing grid data. On the front end, Serenity uses the SlickGrid component.

## Features

#### Row Grouping

Rows are grouped client side in the browser and are set in `Grid.ts` files. You must first register the grouping plugin in `createSlickGrid` function and then you can pass your grouping configuration to the `view.setGrouping` function.

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
                    getter: 'FirstName'
                }
            ]);
        }
    });    
}
```



