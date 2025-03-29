## Key Learnings

### 1. `top: 0; left: 0;` - Why?
```css
.modal {
    top: 0;
    left: 0;
}
```
- **Purpose**: Ensures that the modal covers the entire screen.
- **Effect**: Places the modal at the top-left corner of the viewport.
- **Usage**: Combined with `width: 100%` and `height: 100%`, it creates a full-screen overlay.

### 2. `position: relative;` vs. `position: absolute;`
```css
.modalcontent {
    position: relative;
}
.close {
    position: absolute;
    right: 10px;
    top: 5px;
}
```
- **Parent (`relative`)**: Keeps the child positioned within the modal content.
- **Child (`absolute`)**: Moves freely inside the parent while being positioned relative to it.
- **Usage**: Ensures that the close button appears inside the modal at the top right.

### 3. `:target` - How Does It Work?
```css
#modal:target {
    display: flex;
}
```
- **Purpose**: Selects an element when it is targeted by a URL fragment (e.g., `#modal`).
- **Effect**: When the link `<a href="#modal">` is clicked, the modal appears.
- **Limitation**: Clicking outside the modal does not close it (requires JavaScript for that functionality).

### 4. `display: none;` vs. `display: block;`
```css
.modal {
    display: none;
}
#modal:target {
    display: flex;
}
```
- **`display: none;`**: Hides the modal by default.
- **`display: flex;`**: Makes it visible when targeted.
- **Effect**: The modal appears when the target condition is met.

### 5. `:checked` - How Does It Work?
```css
#modal-toggle:checked + .modal {
    display: flex;
}
```
- **Purpose**: Shows the modal when the checkbox is checked.
- **Effect**: Clicking the label toggles the modal's visibility.
- **Advantage**: Allows toggling without JavaScript.

---

## Code Explanation (Line by Line)

### 1. Opening the Modal with an Anchor (`:target` Approach)
```html
<a href="#modal">Open Modal</a>
```
- Clicking this link targets `#modal`, triggering `:target` styles.

### 2. Closing the Modal (`:target` Approach)
```html
<a href="#" class="close">&times;</a>
```
- Clicking this link removes the `#modal` fragment from the URL, hiding the modal.

### 3. Opening and Closing the Modal (`:checked` Approach)
```html
<label for="modal-toggle">Open Modal</label>
<input type="checkbox" id="modal-toggle">
```
- **Label**: Clicking it toggles the checkbox state.
- **Checkbox (`:checked`)**: Controls modal visibility.
- **Closing**: Clicking the `&times;` label hides the modal.

### 4. Styling the Modal
```css
.modal {
    display: none;
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0, 0, 0, 0.4);
}
```
- **`display: none;`**: Initially hides the modal.
- **`position: fixed;`**: Keeps it centered even when scrolling.
- **`background: rgba(0, 0, 0, 0.4);`**: Adds a semi-transparent overlay.

---
![Screenshot 2025-03-26 130800](https://github.com/user-attachments/assets/8d27f962-01fc-41f9-9824-f56f84c3f802)

