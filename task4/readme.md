## Key Learnings
The following CSS concepts were applied and learned:
1. **Flexbox for Navigation Layout** - The navigation menu is arranged using `display: flex`.
2. **Positioning Elements** - The `position: relative` and `position: absolute` properties help position submenus properly.
3. **Dropdown Visibility Handling** - `opacity`, `visibility`, and `transition` are used to smoothly reveal the submenu.
4. **Hover Effects** - The submenu appears when the user hovers over the parent menu item.

---

## Explanation of the CSS Code

```css
.menu {
    display: flex;
    list-style: none;
    padding: 20px;
    margin: 0;
}
```
### Explanation:
- `display: flex;` → Makes the menu items align in a row.
- `list-style: none;` → Removes bullet points from the list.
- `padding: 20px;` → Adds space inside the menu.
- `margin: 0;` → Removes any default margin around the list.

```css
.menu li {
    position: relative;
    padding: 10px;
}
```
### Explanation:
- `position: relative;` → Ensures submenu items are positioned relative to their parent `li`.
- `padding: 10px;` → Adds space around each menu item.

```css
ul li ul {
    position: absolute;
    top: 100%;
    left: 0;
    background-color: blueviolet;
    list-style: none;
    padding: 0;
    margin: 0;
    width: 150px;
    opacity: 0; /* Make submenu invisible */
    visibility: hidden; /* Prevent interactions */
    transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
}
```
### Explanation:
- `position: absolute;` → Ensures the submenu appears directly below the parent item.
- `top: 100%; left: 0;` → Positions the submenu just below the parent menu item.
- `background-color: blueviolet;` → Sets the background color of the submenu.
- `list-style: none; padding: 0; margin: 0;` → Removes default list styling.
- `width: 150px;` → Defines a fixed width for the submenu.
- `opacity: 0; visibility: hidden;` → Initially hides the submenu.
- `transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;` → Smoothly fades in the submenu when it appears.

```css
ul li ul li {
    padding: 10px;
    white-space: nowrap;
}
```
### Explanation:
- `padding: 10px;` → Adds spacing around submenu items.
- `white-space: nowrap;` → Ensures text does not wrap to the next line.

```css
ul li:hover ul {
    opacity: 1;
    visibility: visible;
}
```
### Explanation:
- `ul li:hover ul {}` → Targets the submenu when the user hovers over the parent `li`.
- `opacity: 1; visibility: visible;` → Makes the submenu visible when hovered.

---

