# Grid Toolbar

The Grid Toolbar allows you to perform tasks on a Grid like creating a new record or selecting and configuring column orders. To create or modify buttons you must override the getButtons\(\) function in the Gri

##### Remove the Toolbar Buttons

To remove the Toolbar buttons from a Grid, override the `getButtons()` function to return null in an EntityGrid TypeScript file like below:

```typescript
protected getButtons(): Serenity.ToolButton[] {
    return null;
}
```

> When removing both the Quick Search and Toolbar Buttons, the area the toolbar occupies above the Grid is hidden.

Hide the Add Button

To hide the New record button you can use the following code in the Grid.cs file:

```typescript
protected getButtons(): Serenity.ToolButton[] {
    var buttons = super.getButtons();

    buttons.splice(Q.indexOf(buttons, x => x.cssClass == "add-button"), 1);
}
```



