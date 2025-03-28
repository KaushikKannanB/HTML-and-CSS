
## Key Learnings

### **1. Key Conditions for `position: sticky` to Work Properly:**
- **Parent must allow scrolling**  
  The sidebar’s parent container should either have a fixed height (`height: 100vh`) or an overflow property that allows scrolling (`overflow-y: auto`).
- **If the parent has `flex: 1;` but no height constraint,** the sidebar may not stick because its reference point keeps shifting.
- **Top value must be defined**  
  Setting `top: 50px;` ensures the sidebar stays `50px` below the viewport when scrolling.
- **Parent should not have `overflow: hidden;`**  
  If the immediate parent has `overflow: hidden;`, the sticky behavior won’t work because the sidebar needs to remain visible.

---

### **2. Key Conditions for `position: fixed` Header:**
- **Fixed positioning removes the element from the normal document flow**  
  The `header` is always visible at the top and does not move when scrolling.
- **It requires a height and full width**  
  Example:
  ```css
  header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 50px;
      background: black;
      z-index: 1000;
  }
  ```
- **Other content should be pushed down to avoid overlap**  
  The `margin-top: 50px;` on `.layout` ensures content starts below the fixed header.

---

### **3. Key Conditions for `:target` CSS-Based Navigation:**
- **Targeting sections makes them visible when clicked**  
  Example:
  ```css
  #home:target, #about:target, #contact:target {
      visibility: visible;
      opacity: 1;
      transform: translateY(0);
  }
  ```
- **The default state of sections should be hidden**  
  Sections are initially hidden using:
  ```css
  .page {
      visibility: hidden;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.5s ease, transform 0.5s ease;
  }
  ```
- **Clicking on a link (e.g., `<a href='#home'>`) triggers visibility changes**  
  This creates a smooth, JavaScript-free page transition.

---

### **4. Key Conditions for Card Hover Effects:**
- **Adding shadows on hover improves UI interaction**  
  Example:
  ```css
  .card:hover {
      box-shadow: 0 8px 16px 0 rgba(0,0,0,0.6);
  }
  ```
- **Ensuring consistent styling**  
  Cards have `box-shadow` and `transition` properties to make hover effects smooth.

---

## Conclusion
This project successfully demonstrates the use of `position: sticky;`, `position: fixed;`, and `:target` navigation. By understanding the above conditions, you can effectively implement similar layouts in future web projects.

