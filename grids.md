# Grids

### Remove the Quick Search

To remove the Quick Search from a Grid, override the `createQuickSearchInput()` function to do nothing in an EntityGrid TypeScript file like below:

```js
protected createQuickSearchInput() { }
```

### Remove the Toolbar Buttons

To remove the Toolbar buttons from a Grid, override the getButtons\(\) function to return null in an EntityGrid TypeScript file like below:

```js
protected getButtons() {
    return null;
}
```

> When removing both the Quick Search and Toolbar Buttons, the area the toolbar occupies above the Grid is hidden.



