
## Text input for **name**

An **input** in HTML is made using the *`<input>`* tag. For example:
```HTML
<input type="text">
```

This creates a basic text box like this:
<input type="text">

Now, to make it more useful, we add:
• A **label** to describe what the input is for
• A **name** or **id** to identify it
• A **placeholder** (optional) to show sample text inside the box

```HTML
<label for="name">Name:</label>
<input type="text" id="name" name="name" placeholder="Enter your name">
```
<label for="name">Name:</label>
<input type="text" id="name" name="name" placeholder="Enter your name">


> NOTE : `for="..."` attribute in `<label>` tag must be equal `id="..."` attribute in `<input>`
****

## E-mail input for **email**

```HTML
<label for="email">E-mail:</label>
<input type="email" id="user-email" name="email" placeholder="Enter your email">

```
<label for="email">E-mail:</label>
<input type="email" id="user-email" name="email" placeholder="Enter your email">


> same as previous
****

## Text area for **message**
A `<textarea>` is used for **multi-line text input**, like a message box. It’s different from `<input>` because it **doesn’t use** type and has **rows** and **cols** to control its size.

**Basic Example:**
```HTML
<label for="message">Message:</label>
<textarea id="message" name="message" rows="4" cols="30" placeholder="Enter your message"></textarea>
```

<label for="message">Message:</label>
<textarea id="message" name="message" rows="4" cols="30" placeholder="Enter your message"></textarea>
****

## **Submit** button

A **submit button** (using `<button>` or `<input type="submit">`)

> `<button>`
<button>Submit</button>

> `<input>`
<input type="Submit">


*P.s button: Can contain **text, icons, or images** inside. and can have different type values (submit, reset, button). Also it's more flexible for styling and customization.
input: Default behavior: submits the form immediately. Text inside it is set using the value attribute. Cannot contain other elements (like icons or images).

