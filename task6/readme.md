## Key Learnings

### 1. `display: none` vs `visibility: hidden`
- `display: none;` completely removes an element from the DOM flow. It does not take up space.
- `visibility: hidden;` makes the element invisible but still occupies space in the layout.
- Here, `display: none;` is used for hiding the radio buttons, while `visibility: hidden;` is used to initially hide the tab content.

### 2. `opacity: 0`
- Makes an element fully transparent but still interactive (unlike `display: none` which removes interaction).
- Here, opacity is combined with `visibility: hidden;` to create a smooth transition effect.

### 3. `translateX()` and `translateY()`
- `transform: translateY(10px);` moves the element 10px downwards.
- When active, it is reset to `translateY(0);`, giving a subtle animation effect.

### 4. `input:checked`
- Used to detect when a radio button is selected.
- When a radio input is checked, the adjacent `label` and `content` change styles, making the corresponding tab visible.

### 5. `input[type="radio"] { display: none; }`
- Hides the radio buttons visually while keeping them functional.
- Labels act as the tab triggers, linked via the `for` attribute.

---

## Explanation of Code

### 1. **Basic Styling**
```css
body {
    font-family: Arial, Helvetica, sans-serif;
}
```
- Sets a clean font style for better readability.

### 2. **Styling the Tabs**
```css
.tablabel {
    border-radius: 5px;
    margin: 5px;
    padding: 15px;
    transition: all 0.4s;
    background: darkgray;
}
```
- `border-radius: 5px;` gives rounded corners.
- `margin` and `padding` create spacing around the label.
- `transition: all 0.4s;` smoothens background and shadow changes.

#### **Hover Effect**
```css
.tablabel:hover {
    background: rgba(0,0,0,0.6);
    box-shadow: 0 8px 16px 0 rgba(0,0,0,0.6);
}
```
- Changes the background on hover.
- Adds a shadow effect for better UI feedback.

### 3. **Content Styling**
```css
.content {
    visibility: hidden;
    opacity: 0;
    height: 0;
    border: 2px solid black;
    padding: 22px;
    margin-top: 10px;
    border-radius: 5px;
    text-align: center;
    transform: translateY(10px);
    transition: opacity 0.3s ease, transform 0.3s ease;
}
```
- Initially hidden (`visibility: hidden; opacity: 0; height: 0;`).
- `transform: translateY(10px);` moves it slightly downward.
- `transition` ensures a smooth fade-in effect.

### 4. **Revealing Active Content**
```css
input[type="radio"]:checked + label + .content {
    visibility: visible;
    opacity: 1;
    height: auto;
    transform: translateY(0);
    transition: opacity 0.3s ease, transform 0.3s ease;
}
```
- When a radio button is checked, the adjacent content becomes visible.
- `height: auto;` allows the content to expand naturally.
- `transform: translateY(0);` resets position for a smooth animation.

### 5. **Tab Layout (Flexbox)**
```css
.tabs {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 5px;
}
```
- `display: flex;` arranges tabs in a row.
- `justify-content: center;` centers them horizontally.
- `gap: 5px;` adds spacing between tabs.

### 6. **Hiding Radio Buttons**
```css
input[type="radio"] {
    display: none;
}
```
- Hides the radio buttons but keeps their functionality intact.
- Labels act as their visual representation.

---
![Screenshot 2025-03-26 174954](https://github.com/user-attachments/assets/be362107-5b57-463c-964f-844642f9ea77)
