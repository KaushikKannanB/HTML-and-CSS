## Key Learnings & Explanations

### 1. `margin: 0;`
   - This removes all default margin space around the body to ensure elements align correctly.

### 2. `z-index`
   - Determines the stacking order of elements.
   - Higher values appear above lower ones.
   - Example: `z-index: 1000;` ensures the header stays on top of all other elements.

### 3. `height: 100vh;`
   - Sets the height of an element to **100% of the viewport height**.
   - Ensures the full screen is utilized properly.

### 4. `flex: 1;`
   - Distributes available space among flex children.
   - Makes the container expand to fill remaining space dynamically.

### 5. `height: calc();`
   - Example: `height: calc(100vh - 50px);`
   - Subtracts header height from the total screen height.
   - Used to dynamically calculate height based on other elements.

### 6. `overflow-y: auto;`
   - Enables vertical scrolling only when content exceeds the container’s height.
   - Prevents unnecessary scrollbars when content fits.

### 7. Parent & Child Scrollable Condition
   - The parent container must have `overflow: auto;` or `overflow: scroll;`.
   - The child element must have a larger height than its parent to trigger scrolling.

### 8. Why Use `grid-template-columns: repeat(3, 1fr);` Over `auto auto auto`?
   - `repeat(3, 1fr);` ensures **equal distribution of space**.
   - `auto auto auto;` sizes columns based on content, leading to uneven widths.

### 9. Extra Space (`.space`)
   - A div with `height: 2000px;` ensures enough scrollable area for testing sticky behavior.

## Key CSS & HTML Code Breakdown

### Sticky Header
```css
header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 50px;
    background: black;
    color: white;
    z-index: 1000;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

### Sticky Sidebar
```css
aside {
    position: sticky;
    top: 50px;
    width: 180px;
    height: calc(100vh - 50px);
    overflow-y: auto;
    background-color: #f4f4f4;
    border-right: 2px solid black;
}
```

### Scrollable Content
```css
.containerbox {
    flex: 1;
    overflow-y: auto;
    padding: 30px;
}
```

### Content Grid Layout
```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### Overlapping Boxes with `z-index`
```css
.box1 {
    width: 40px;
    height: 40px;
    background-color: blueviolet;
    position: absolute;
    top: 10px;
    left: 10px;
    z-index: 2;
}
.box2 {
    width: 80px;
    height: 80px;
    background-color: cadetblue;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
}
```

![Screenshot 2025-03-27 232742](https://github.com/user-attachments/assets/53741c12-5328-40a0-b5cb-3e0f95c0a517)

![Screenshot 2025-03-27 232826](https://github.com/user-attachments/assets/999aba05-199a-43d3-bfd4-df47bdca083a)
