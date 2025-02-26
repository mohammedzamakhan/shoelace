# Input

[component-header:sl-input]

Inputs collect data from the user.

```html preview
<sl-input></sl-input>
```

?> This component doesn't work with standard forms. Use [`<sl-form>`](/components/form.md) instead.

?> Please refer to the section on [form control validation](/components/form?id=form-control-validation) to learn how to do client-side validation.

## Examples

### Placeholders

Use the `placeholder` attribute to add a placeholder.

```html preview
<sl-input placeholder="Type something"></sl-input>
```

### Clearable

Add the `clearable` prop to add a clear button when the input has content.

```html preview
<sl-input placeholder="Clearable" clearable></sl-input>
```

### Toggle Password

Add the `toggle-password` prop to add a toggle button that will show the password when activated.

```html preview
<sl-input type="password" placeholder="Password Toggle" size="small" toggle-password></sl-input>
<br>
<sl-input type="password" placeholder="Password Toggle" size="medium" toggle-password></sl-input>
<br>
<sl-input type="password" placeholder="Password Toggle" size="large" toggle-password></sl-input>
```

### Pill

Use the `pill` prop to give inputs rounded edges.

```html preview
<sl-input placeholder="Small" size="small" pill></sl-input>
<br>
<sl-input placeholder="Medium" size="medium" pill></sl-input>
<br>
<sl-input placeholder="Large" size="large" pill></sl-input>
```

### Disabled

Use the `disabled` attribute to disable an input.

```html preview
<sl-input placeholder="Disabled" size="small" disabled></sl-input>
<br>
<sl-input placeholder="Disabled" size="medium" disabled></sl-input>
<br>
<sl-input placeholder="Disabled" size="large" disabled></sl-input>
```

### Sizes

Use the `size` attribute to change an input's size.

```html preview
<sl-input placeholder="Small" size="small"></sl-input>
<br>
<sl-input placeholder="Medium" size="medium"></sl-input>
<br>
<sl-input placeholder="Large" size="large"></sl-input>
```

### Prefix & Suffix Icons

Use the `prefix` and `suffix` slots to add icons.

```html preview
<sl-input placeholder="Small" size="small">
  <sl-icon name="tag" slot="prefix"></sl-icon>
  <sl-icon name="gear" slot="suffix"></sl-icon>
</sl-input>
<br>
<sl-input placeholder="Medium" size="medium">
  <sl-icon name="tag" slot="prefix"></sl-icon>
  <sl-icon name="gear" slot="suffix"></sl-icon>
</sl-input>
<br>
<sl-input placeholder="Large" size="large">
  <sl-icon name="tag" slot="prefix"></sl-icon>
  <sl-icon name="gear" slot="suffix"></sl-icon>
</sl-input>
```

### Labels

Use the `label` attribute to give the input an accessible label.

```html preview
<sl-input label="Name"></sl-input>
<br>
<sl-input type="email" label="Email" placeholder="bob@example.com"></sl-input>
```

### Help Text

Add descriptive help text to an input with the `help-text` slot.

```html preview
<sl-input label="Nickname">
  <div slot="help-text">What would you like people to call you?</div>
</sl-input>
```

### Inputs with Dropdowns

Dropdowns can be used in the `prefix` or `suffix` slot to make inputs more versatile. Make sure to use the `hoist` prop so the dropdown breaks out of the input's overflow.

```html preview
<div class="input-dropdowns">
  <sl-input type="tel" label="Phone">
    <sl-icon slot="prefix" name="telephone"></sl-icon>
    <sl-dropdown slot="suffix" placement="bottom-end" hoist>
      <sl-button slot="trigger" caret type="text" size="small">Home</sl-button>
      <sl-menu>
        <sl-menu-item checked>Home</sl-menu-item>
        <sl-menu-item>Mobile</sl-menu-item>
        <sl-menu-item>Work</sl-menu-item>
      </sl-menu>
    </sl-dropdown>
    <div slot="help-text">
      Please enter a phone number where we can reach you.
    </div>
  </sl-input>
</div>

<script>
  const container = document.querySelector('.input-dropdowns');
  const dropdown = container.querySelector('sl-dropdown');
  const trigger = dropdown.querySelector('sl-button');

  dropdown.addEventListener('slSelect', event => {
    const selectedItem = event.detail.item;
    trigger.textContent = selectedItem.textContent;
    [...dropdown.querySelectorAll('sl-menu-item')].map(item => item.checked = item === selectedItem);
  });
</script>

<style>
  .input-dropdowns sl-dropdown {
    margin-right: .25rem;
  }
</style>
```

[component-metadata:sl-input]
