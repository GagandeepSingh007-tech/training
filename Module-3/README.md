Welcome to module-3: Inroduction to HTML & Web Basics

# 1. Introduction to HTML & Web Basics

## HTML: 
Hyper Text Markup Language is the standard markup language used to structure content on the web

## Browser Rendering: 
The browser fetches the the raw HTML, parses the tags from top to bottom, builds the DOM (Document Object Model) tree, and render it visually.

## Structure of HTML document:
1. **<!DOCTYPE html>:** Declares modern  HTML5.
2. **<html>:** Root container.
3. **<head>:** Holds the page metadat.
4. **<body>:** Holds all visible webpage content.
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

## HTML Tags:
To build structural content within the <body>, specific semantic tags are utilizes.
1. **Heading(<h1> to <h6>):** Defines structural hierarchy <h1> is the main title; <h6> is the lowest sub-heading.
   * **Attributeds:**
     * **id:** Assigns a unique identifier to a single heading.
     * **class:** Assigns a style category shared by a multiple elements.

2. **Paragraph tag (<p>):** Structures a block of body test with automatic vertical spacing.
   * **attributes:**
     * **class:** Group paragraphs together for custom styling.
     * **title:** Displays a pop-up when hovered over by a mouse.

3. **List Tags (<ul>, <ol>, <dl>, <li>):** Organizes content into bulleted or numbered items
   1. **Unorderd list (<ul>):** For collections where the order of items does not matters. Displays the bulleted points.
      * **Attributes:**
        * **type:** To change bullets to disc, circle, or square.
   2. **Ordered llist <ol>:** For sequentical steps or ranked items. Displays with numbers or letters.
      * **Attributes:**
        * **type:** Sets format (1 for numbers A/a for letters, I/i for roman numericals)
        * **start:** Sets the starting number value.
        * ""Reversed:** Reverse the counting order.
   3. **Descriptive list (<dl>):** For glossaries, dictionaries, or key-value pairs.

4. **Link Tag (<a>):** Creates ahyperlink to navigate to another page.
   * **Attributes:** href setd the description URL; target=="_blanck" opens it in a new tab.

5. **Image Tag (<img>):** A self closing element that embeds graphic files.
   * **Attributes:** src specifies the file path; alt provides backup description test; width/height sets pixel dimensions.

# 2. Introduction to HTML & Web Basics

## Forms and Input types
HTML forms collect the user information to send to a server for processing. The structural area is defined by the <form> tag, which can uses several key attributes
* **action:** Specifies the file destination or URL where data is sent.
* **method:** Controls how  data is sent or URL where data is sent. Making it visible. POST embeds data securily within the request body, keeping it hidden from the URL (required for logins, registrations and payments.
* **autocomplete:** Configures the browser's autofill behavior to be ON or OFF.
* **target:** Specifies where to display the response after submission.
* **name:** Assigns an identifier name to the form.

## Input Types:
| # | Type | Tag Code | Typical Meaning / Function |
| :--- | :--- | :--- | :--- |
| 1 | *Text* | type="text" | Enters a single line of standard text. |
| 2 | *Password* | type="password" | Obscures characters to protect credentials. |
| 3 | *Number* | type="number" | Restricts input strictly to numeric values. |
| 4 | *Email* | type="email" | Validates standard email addresses. |
| 5 | *Date* | type="date" | Provides a native calendar date picker. |
| 6 | *Time* | type="time" | Renders a structured time selection tool. |
| 7 | *Color* | type="color" | Displays a native color picker tool. |
| 8 | *File* | type="file" | Allows local file uploads. |
| 9 | *Radio* | type="radio" | Permits selecting only one option out of a group sharing the exact same name. |
| 10 | *Checkbox* | type="checkbox" | Allows multiple independent selections concurrently. |
| 11 | *Submit* | type="submit" | Transmit form data to the designated action file. |
| 12 | *Reset* | type="reset" | Purges all input fields back to their blank or default states. |
| 13 | *Button* | type="button" | Creates a generic clickable button for custom scripting. |
| 14 | *Search* | type="search" | Standardsizes an optimized search entry box. |
| 15 | *URL* | type="url" | Accepts only properly formatted website address. |
| 16 | *Telephone* | type="tel" | Captures phone numbers. |
| 17 | *Range* | type="range" | Renders a draggable slider bounded by min and max limits. |
| 18 | *Hidden* | type="hidden" | Stores internal administrative data hidden from the user interface. |

```html
<!DOCTYPE DOCTYPE html>
<html>
<head><title>Form Demo</title></head>
<body>
<form action="submit.html" method="post">
  <fieldset>
    <legend>Student Form</legend>
    <label for="n">Name:</label>
    <input type="text" id="n" required><br>
    <label for="e">Email:</label>
    <input type="email" id="e"><br>
    <label for="p">Password:</label>
    <input type="password" id="p"><br>
    <label>Gender:</label>
    <input type="radio" id="m" name="g"><label for="m">Male</label>
    <input type="radio" id="f" name="g"><label for="f">Female</label><br>
    <label><input type="checkbox"> Reading</label><br>
    <label for="s">State:</label>
    <select id="s">
      <option>Punjab</option>
    </select><br>
    <label for="b">Bio:</label>
    <textarea id="b" rows="2"></textarea><br>
    <input type="submit" value="Submit">
    <input type="reset" value="Reset">
  </fieldset>
</form>
</body>
</html>
```

## Supplementary Form Elemnts
Beyond standard inputs, specialized tags build out complex layouts:

*   **<label>:** Provides a description for an input field, expanding click target zones when linked using for and id attributes.
*   **<textarea>:** Allocates a multi-line, scrollable text box for longer blocks like addresses or feedback.
*   **<select> & <option> shadow:** Generates space-saving drop-down option choice menus.
*   **<fieldset> & <legend>:** Groups related form elements within a visible border frame topped by an integrated title.

---

## Form Control Attributes
Validation rules and specific element behaviors are configured directly using attributes:

*   **placeholder / value:** Displays temporary content hint text or sets a hard default value.
*   **required / disabled:** Enforces fields as compulsory or disables them completely from data submission.
*   **readonly:** Prevents users from altering the field content while keeping it viewable.
*   **maxlength / minlength:** Binds maximum or minimum characters limit for text entries.
*   **min / max / step:** Establishes boundaries and intervals for numeric and range controls.
*   **checked / selected:** Pre-selects checkboxes, radio buttons, or dropdown list choices upon page load.
*   **autofocus / multiple:** Grants immediate typing focus on page load or permits multiple file/email entries.

## Semantic HTML Tags:

Semantic elements clearly describe their meaning to both the browser and the developer, providing clear structural architecture to a webpage:

*   **<header>:** Houses introductory elements of a page or section, typically containing main logos, branding, titles, or site-wide search tools.
*   **<nav>:** Reserves a dedicated structural area specifically for primary website navigation links, signaling to screen readers where the site menu resides.
*   **<section>:** Splits webpage layout into thematic, organized content blocks, acting as a container for grouping distinct content topics.
*   **<article>:** Wraps independent, self-contained compositions meant to be independently reusable or distributable on their own.
*   **<footer>:** Anchors base components at the bottom of a webpage or section, typically carrying copyright statements, legal notices, privacy links, and contact information.
```html
<!DOCTYPE html>
<html>
<head><title>Semantic Layout</title></head>
<body>
  <header>
    <h1>GNDEC Web Basics</h1>
    <nav>
      <a href="#">Home</a> | <a href="#">About</a>
    </nav>
  </header>
  
  <section>
    <article>
      <h2>Semantic Layout Architecture</h2>
      <p>Semantic tags describe their purpose to browsers and SEO tools.</p>
    </article>
  </section>
  
  <footer>
    <p>&copy; 2026 GNDEC Ludhiana</p>
  </footer>
</body>
</html>
```
# 3. Basic Styling Using inline & internal CSS

## CSS:
CSS (Cascadng Style Sheets) controls the visual presentation of a webpage (color, fonts, layout), While HTML provides the structure.

## Inline CSS:
Inline CSS applies unique styles directly to a single HTML element using the style attribute inside the elements opening tag.
```CSS
<h1 style="color:blue; text-align:center;">
```
## Internal CSS
Internal CSS styles an entire single HTML document from one centralized location. It is declared inside inside a <style> tag olaces within the document <head> section.
```CSS
<head>
  <style>
    body{
      background-color: #f4f4f4;
      }
    h1{
      color: navy;
    }
  </style>
</head>
```

## Personal Portfolio Website

---

## 🌐 Personal Portfolio Website in HTML (multipage)

### 🏷️ Tags Used

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
| `<section>` | Group related content into separate section of the webpage. |
| `<table>` | Creates a table to display data in rows and columns. |
| `<thead>` | Groups header section of a table. |
| `<tbody>` | Groups the main content of the table. |
| `<tr>` | Defines a row in table. |
| `<th>` | Defines a table header cell. |
| `<td>` | Defines a table data cell. |
| `<span>` | An inline container used to style or manipulate small portions of text. |
| `<footer>` | Represents the footer section of the webpage. |
| `<img>` | Embeds images into the webpage. |


