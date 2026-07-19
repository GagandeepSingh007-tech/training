# Module 3: Introduction to HTML & Web Basics

Welcome to Module 3. This section contains my training notes on web form structures, semantic layout rules, and core elements.

---

##  1. Introduction to HTML & Web Basics

###  HTML
HyperText Markup Language is the standard markup language used to structure content on the web.

###  Browser Rendering
The browser fetches the raw HTML, parses the tags from top to bottom, builds the DOM (Document Object Model) tree, and renders it visually.

###  Structure of an HTML Document
1. **`<!DOCTYPE html>`**: Declares modern HTML5.
2. **`<html>`**: Root container.
3. **`<head>`**: Holds the page metadata.
4. **`<body>`**: Holds all visible webpage content.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <!-- Content goes here -->
</body>
</html>
```
##  HTML Tags
To build structural content within the `<body>`, specific semantic tags are utilized.

### 1. Heading Elements (`<h1>` to `<h6>`)
Defines structural hierarchy. `<h1>` is the main title, and `<h6>` is the lowest sub-heading.
*   **Attributes:**
    *   **`id`**: Assigns a unique identifier to a single heading.
    *   **`class`**: Assigns a style category shared by multiple elements.

### 2. Paragraph Tag (`<p>`)
Structures a block of body text with automatic vertical spacing.
*   **Attributes:**
    *   **`class`**: Groups paragraphs together for custom styling.
    *   **`title`**: Displays a pop-up when hovered over by a mouse.

### 3. List Tags (`<ul>`, `<ol>`, `<dl>`, `<li>`)
Organizes content into bulleted or numbered items.
1.  **Unordered List (`<ul>`)**: For collections where the order of items does not matter. Displays bulleted points.
    *   **Attributes:**
        *   **`type`**: To change bullets to disc, circle, or square.
2.  **Ordered List (`<ol>`)**: For sequential steps or ranked items. Displays numbers or letters.
    *   **Attributes:**
        *   **`type`**: Sets format (1 for numbers, A/a for letters, I/i for Roman numerals).
        *   **`start`**: Sets the starting number value.
        *   **`reversed`**: Reverses the counting order.
3.  **Descriptive List (`<dl>`)**: For glossaries, dictionaries, or key-value pairs.

### 4. Link Tag (`<a>`)
Creates a hyperlink to navigate to another page.
*   **Attributes:**
    *   **`href`**: Sets the destination URL.
    *   **`target="_blank"`**: Opens the link in a new browser tab.

### 5. Image Tag (`<img>`)
A self-closing element that embeds graphic files.
*   **Attributes:**
    *   **`src`**: Specifies the file path of the image.
    *   **`alt`**: Provides backup description text for accessibility.
    *   **`width` / `height`**: Sets exact pixel dimensions.
 
## 📋 2. HTML Form Input Elements
Forms are critical for collecting user data. Here is a comprehensive reference directory of native HTML input types:

| # | Type | Tag Code | Typical Meaning / Function |
| :--- | :--- | :--- | :--- |
| 1 | **Text** | `type="text"` | Enters a single line of standard text. |
| 2 | **Password** | `type="password"` | Obscures characters to protect credentials. |
| 3 | **Number** | `type="number"` | Restricts input strictly to numeric values. |
| 4 | **Email** | `type="email"` | Validates standard email addresses. |
| 5 | **Date** | `type="date"` | Provides a native calendar date picker. |
| 6 | **Time** | `type="time"` | Renders a structured time selection tool. |
| 7 | **Color** | `type="color"` | Displays a native color picker tool. |
| 8 | **File** | `type="file"` | Allows local file uploads. |
| 9 | **Radio** | `type="radio"` | Permits selecting only one option out of a group sharing the exact same name. |
| 10 | **Checkbox** | `type="checkbox"` | Allows multiple independent selections concurrently. |
| 11 | **Submit** | `type="submit"` | Transmits form data to the designated action file. |
| 12 | **Reset** | `type="reset"` | Purges all input fields back to their blank or default states. |
| 13 | **Button** | `type="button"` | Creates a generic clickable button for custom scripting. |
| 14 | **Search** | `type="search"` | Standardizes an optimized search entry box. |
| 15 | **URL** | `type="url"` | Accepts only properly formatted website addresses. |
| 16 | **Telephone** | `type="tel"` | Captures phone numbers. |
| 17 | **Range** | `type="range"` | Renders a draggable slider bounded by min and max limits. |
| 18 | **Hidden** | `type="hidden"` | Stores internal administrative data hidden from the user interface. |

---

##  Supplementary Form Elements
Beyond standard inputs, specialized tags build out complex layouts:

*   **`<label>`:** Provides a description for an input field, expanding click target zones when linked using `for` and `id` attributes.
*   **`<textarea>`:** Allocates a multi-line, scrollable text box for longer blocks like addresses or feedback.
*   **`<select>` & `<option>`:** Generates space-saving drop-down option choice menus.
*   **`<fieldset>` & `<legend>`:** Groups related form elements within a visible border frame topped by an integrated title.

---

## 🛠️ Form Control Attributes
Validation rules and specific element behaviors are configured directly using attributes:

*   **`placeholder` / `value`:** Displays temporary content hint text or sets a hard default value.
*   **`required` / `disabled`:** Enforces fields as compulsory or disables them completely from data submission.
*   **`readonly`:** Prevents users from altering the field content while keeping it viewable.
*   **`maxlength` / `minlength`:** Binds maximum or minimum character limits for text entries.
*   **`min` / `max` / `step`:** Establishes boundaries and intervals for numeric and range controls.
*   **`checked` / `selected`:** Pre-selects checkboxes, radio buttons, or dropdown list choices upon page load.
*   **`autofocus` / `multiple`:** Grants immediate typing focus on page load or permits multiple file/email entries.

---

##  Semantic HTML Tags
Semantic elements clearly describe their meaning to both the browser and the developer, providing clear structural architecture to a webpage:

*   **`<header>`:** Houses introductory elements of a page or section, typically containing main logos, branding, titles, or site-wide search tools.
*   **`<nav>`:** Reserves a dedicated structural area specifically for primary website navigation links, signaling to screen readers where the site menu resides.
*   **`<section>`:** Splits webpage layout into thematic, organized content blocks, acting as a container for grouping distinct content topics.
*   **`<article>`:** Wraps independent, self-contained compositions meant to be independently reusable or distributable on their own.
*   **`<footer>`:** Anchors base components at the bottom of a webpage or section, typically carrying copyright.

##  Basic Styling using inline & internal CSS
CSS (Cascading Style Sheets) controls the visual presentation of a webpage (color, fonts, layout), while HTML provides the structure.

### Inline CSS:
Inline CSS applies unique styles directly to a single HTML element using the `style` attribute inside the element's opening tag.

**Syntax example:**
```html
<h1 style="color: blue; text-align: center;">
```

### Internal CSS:
Internal CSS styles an entire single HTML document from one centralized location. It is declared inside a <style> tag placed within the document <head> section.
```CSS
<head>
<style>
body {
    background-color: #f4f4f4;
}
h1 {
    color: navy;
}
</style>
</head>
```
##  Personal Portfolio Website in HTML (multipage)

###  Tags Used

| HTML Tag | Explanation |
| :--- | :--- |
| `<!DOCTYPE html>` | Declares the document as an HTML 5 document. |
| `<html>` | The root element that contains the entire HTML page. |
| `<head>` | Contains metadata, title, styles, and other information about the webpage. |
| `<meta>` | Defines metadata such as character encoding and viewport settings. |
| `<title>` | Sets the title of the webpage displayed on the browser tab. |
| `<style>` | Contains internal CSS used to design and format the webpage. |
| `<body>` | Contains all the visible content displayed on the webpage. |
| `<nav>` | Creates a navigation section with links to different parts of the page. |
| `<h1>` | Defines the main heading of a section. |
| `<h2>` | Defines a second-level heading. |
| `<h3>` | Defines the third-level heading. |
| `<a>` | Creates a hyperlink to other pages, sections, or email addresses. |
| `<div>` | A container used to group HTML elements for styling and layout. |
| `<p>` | Defines a paragraph of text. |
| `<pre>` | Displays preformatted text while preserving spaces and line breaks. |
| `<br>` | Inserts a single line break. |
| `<section>` | Groups related content into separate sections of the webpage. |
| `<table>` | Creates a table to display data in rows and columns. |
| `<thead>` | Groups header section of a table. |
| `<tbody>` | Groups the main content of the table. |
| `<tr>` | Defines a row in a table. |
| `<th>` | Defines a table header cell. |
| `<td>` | Defines a table data cell. |
| `<span>` | An inline container used to style or manipulate small portions of text. |
| `<footer>` | Represents the footer section of the webpage. |
| `<img>` | Embeds images into the webpage. |
