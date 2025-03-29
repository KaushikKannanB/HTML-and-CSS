## Key Learnings

### 1. Position Property and Its Options
The `position` property in CSS determines how an element is positioned in a document. Here are the common options:

- **Static (default)**: Elements are positioned according to the normal document flow.
- **Relative**: The element is positioned relative to its normal position.
- **Absolute**: The element is removed from the document flow and positioned relative to its nearest positioned ancestor.
- **Fixed**: The element is positioned relative to the viewport and stays fixed even when scrolling.
- **Sticky**: The element switches between relative and fixed positioning based on the scroll position.

### 2. Overflow: Hidden
The `overflow` property controls what happens when content overflows the dimensions of its container.

- **hidden**: Any content that exceeds the container's dimensions is not displayed.
- **visible**: The overflowing content remains visible.
- **scroll**: Adds a scrollbar to allow scrolling.
- **auto**: Adds a scrollbar only when necessary.

In this project, `overflow: hidden` is used in `.content` to keep the section collapsed until it is expanded.

### 3. Max-Height
The `max-height` property defines the maximum height an element can grow to. It is often used in animations and transitions.

- When `max-height: 0`, the element is collapsed.
- When the checkbox is checked, `max-height: 200px` is applied, making the section expand.
- The transition effect creates a smooth opening and closing effect.

## Key Code Explanations

### Hiding Checkboxes
```css
input[type="checkbox"] {
    display: none;
}
```
CheckBoxes are hidden but still functional, allowing us to use them to trigger the accordion sections.

### Transition Effect
```css
.content {
    max-height: 0;
    overflow: hidden;
    padding: 5px;
    transition: max-height 0.4s ease-in-out, padding 0.4s ease-in-out;
}
```
This smoothly expands the content when triggered.

### Expanding the Section on Click
```css
input[type="checkbox"]:checked + label + .content {
    max-height: 200px;
    border: 1px solid black;
    border-radius: 10px;
    background-color: aliceblue;
}
```
When the checkbox is checked, the associated content expands.

![Screenshot 2025-03-27 010604](https://github.com/user-attachments/assets/863d46b6-c92b-4ab6-9592-5731bdff9a10)
