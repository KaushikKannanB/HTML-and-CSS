## Key Learnings

### 1. Flexbox vs Grid Differences
- **Flexbox** is a one-dimensional layout system (either row or column).
- **Grid** is a two-dimensional layout system (both rows and columns).
- Use **Flexbox** for dynamic content alignment along a single axis (like navbars).
- Use **Grid** for complex layouts requiring explicit rows and columns.

### 2. Understanding CSS Grid Properties
#### a) `grid-template-columns`
```css
.container {
    display: grid;
    grid-template-columns: auto auto auto;
}
```
- Defines how many columns a grid should have.
- `auto auto auto` means three equally spaced columns.
- Responsive media queries adjust column counts dynamically.

#### b) `grid-template-rows`
```css
.container {
    grid-template-rows: 100px 200px;
}
```
- Defines the height of each row.
- Useful for controlling vertical spacing.

#### c) `grid-area`
```css
.card {
    grid-area: 1 / 2 / span 2 / span 3;
}
```
- Specifies where an item is placed in the grid.
- `1 / 2 / span 2 / span 3` means it starts at **row 1, column 2** and spans **2 rows, 3 columns**.

### 3. Responsive Design with Media Queries
#### a) Adjusting Columns for Different Screen Sizes
```css
@media (max-width: 768px) {
    .container {
        grid-template-columns: auto auto;
    }
}
@media (max-width: 600px) {
    .container {
        grid-template-columns: auto;
    }
}
```
- Ensures the layout adapts to smaller screens.
- **768px:** 2 columns, **600px:** 1 column for better readability.

### 4. Styling Enhancements
#### a) Box Shadows and Hover Effects
```css
.card:hover {
    box-shadow: 0 8px 16px 0 rgba(0,0,0,0.6);
}
```
- Creates a **hover effect** that changes the shadow.
- Improves user experience by providing visual feedback.

#### b) Background Colors and Padding
```css
body {
    background-color: rgba(100, 148, 237, 0.488);
}
```
- Uses `rgba()` for **semi-transparent backgrounds**.
- Enhances readability by distinguishing sections.
<br><br>
![Screenshot 2025-03-25 205157](https://github.com/user-attachments/assets/af69ec19-17fd-4332-81d2-ed0272f733c1)
<br><br>

![Screenshot 2025-03-25 204746](https://github.com/user-attachments/assets/17d87f86-0640-489c-a023-5b4b5f64c081)
