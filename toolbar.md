# Grid Toolbar

The Grid Toolbar allows you to perform tasks on a Grid like creating a new record or selecting and configuring column orders.



##### Remove the Toolbar Buttons

To remove the Toolbar buttons from a Grid, override the `getButtons()` function to return null in an EntityGrid TypeScript file like below:

```js
protected getButtons() {
    return null;
}
```

> When removing both the Quick Search and Toolbar Buttons, the area the toolbar occupies above the Grid is hidden.



