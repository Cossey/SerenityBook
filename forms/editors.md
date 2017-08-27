# Form Editors

The following form editors are configured via attributes set on the fields in a `Form.cs` file.

## Text

### String Editor

This allows plain text to be entered.

##### Options

This editor has no configurable options.

### Text Area Editor

This text area editor is mainly used in entering descriptions or multi-line text.

##### Editor Options

| Option | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| Cols | Columns | int |  |
| Rows | Rows | int | Sets the height in rows of the Text Area. |

##### Set a Text Area to 4 Lines in height

This change is made in the `Form.cs` file.

```csharp
[BasedOnRow(typeof(Entities.ExampleRow))]
public class ExampleForm
{
    [TextAreaEditor(Rows = 4)]
    public String ExampleText { get; set; }
}
```

### Email Editor

![](/assets/email.png)

The email editor consists of two texts boxes divided by an at \(@\) symbol. The second box is the domain part of the email address.

##### Options

| Option | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| Domain | Domain | string | Sets the default value of the domain portion of the email address \(second box\). |
| ReadOnlyDomain | Domain Read Only | bool | Makes the domain portion of the email read only. |

##### Make an email editor accept only a particular email domain

```csharp
[FormScript("ExampleForm")]
[BasedOnRow(typeof(Entities.ExampleRow))]
public class ExampleForm
{
    [EmailEditor(Domain = "lockeddomain.com", ReadOnlyDomain = true)]
    public String Email { get; set; }
}
```

![](/assets/emaileditorlocked.png)

### Password Editor

The password editor allows for text to be entered but masked in the form.

![](/assets/passwordeditor.png)

> WARNING: Any Password Editor fields still send their data in plain text format.

##### Options

This editor has no configurable options.

### Masked Editor

The masked editor can restrict the input to a specific set of letters or numbers. Serenity uses the [Masked Input Plugin](http://digitalbush.com/projects/masked-input-plugin/).

##### Options

| Option | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| mask | Mask | String | Input mask. Refer to the Input Mask Grid below for supported syntax. |
| placeholder | Placeholder Text | String | The placeholder character or placeholder text to display. |



##### Input Mask Syntax

| Mask | Type | Info |
| :--- | :--- | :--- |
| a | Alpha Character | Allow Alpha Character Only. |
| 9 | Numeric Character | Allow Numeric Character Only. |
| \* | Alphanumeric Character | Allow Alphanumeric Character. |
| ? | Optional Input | Any values after this mask are considered optional. |



### URL Editor

### 

## Numerical

![](/assets/decint.png)

Numerical fields restrict the input mainly to numerals. In the case of the Decimal Editor, the decimal point is also present.

### Integer Editor

The integer editor only allows for numerals to be entered into a input box.

### Decimal Editor

The Decimal Editor allows for a fractional value to be entered into a form.

##### Minimum and Maximum values

By default the Decimal Editor does not allow negative values. To allow this the `MinValue` and `MaxValue` options must be set.

```csharp
[DecimalEditor(MinValue = "-999.99", MaxValue = "999.99")]
public Decimal ExampleProperty { get; set; }
```

> When setting the `MinValue` and `MaxValue` options, make sure you use the same number of digits in both the minimum and maximum.

##### Decimal places

The decimal places can be configured by setting the `Scale` attribute to the amount of places. For example, to set an input of two decimal places:

```csharp
[DisplayName("Example Property"), Scale(2)]
public Decimal? ExampleProperty
{
    get { return Fields.ExampleProperty[this]; }
    set { Fields.ExampleProperty[this] = value; }
}
```

> In some cases like accounting, you may want to `Scale` to 4 decimal places.

### Phone Editor

The Phone Editor is for telephone fields. This only supports Turkey telephone and mobile number formatting.

##### Options

| Option | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| AllowExtension |  | bool |  |
| AllowInternational |  | bool |  |
| Internal | Internal Number Format | bool | Validates against a valid internal phone number. |
| Mobile | Mobile Format | bool | Validates against a valid mobile number. |
| Multiple |  | bool |  |

## Check/Option

### Boolean Editor

![](/assets/bool.png)

The boolean editor is typically a checkbox field.

### Radio Button Editor

### Check List Editor

## Special

### Check Tree Editor

### Html Content Editor

This editor is used for WYSIWYG content editing.

![](/assets/htmlcontent.png)

##### Options

| Option | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| Cols |  |  |  |
| Rows | Rows | int | Sets the height in rows of the Content Editor. |

## Files and Uploading

### File Upload Editor

![](/assets/fileupload.png)

### Image Upload Editor

![](/assets/filesel.png)

## Date and Time

### Date Time Editor

![](/assets/date.png)

The Date and Time editor allows you to select a date from a drop down.

Options

| Option | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| SqlMinMax |  | bool |  |
| IntervalMinutes | Minute Interval | int | Sets the minute step among the interval time. |
| StartHour | Start Hour | int |  |
| EndHour | End Hour | int |  |
| MinValue | Minimum Value | DateTime |  |
| MaxValue | Maximum Value | DateTime |  |

### Date Year Editor

### Time Editor

## Drop downs

### Enum Editor

### [Lookup Editor](/forms/editors/lookup-editors.md)

![](/assets/lookup.png)

The lookup editor is a drop down that references data from another table in the database. It has a Filter text at the top and can dynamically load additional data. It is the [Select2 ](http://select2.github.io/select2/)drop down for jQuery. Refer to the [Lookup Editors](/lookup-editors.md) section for more information on how to use this Editor.

### 

### 



