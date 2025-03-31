## Code Breakdown

### **1. HTML Structure**
```html
<div class="carousel">
    <div class="slides">
        <input type="radio" name="radio-btn" id="slide1" checked>
        <input type="radio" name="radio-btn" id="slide2">
        <input type="radio" name="radio-btn" id="slide3">
        
        <div class="slide"><img src="image1.jpg" alt="Slide 1"></div>
        <div class="slide"><img src="image2.jpg" alt="Slide 2"></div>
        <div class="slide"><img src="image3.jpg" alt="Slide 3"></div>
    </div>
    <div class="navigation">
        <label for="slide1"></label>
        <label for="slide2"></label>
        <label for="slide3"></label>
    </div>
</div>
```
### **Explanation:**
- The `.carousel` container holds the slides.
- The `.slides` div contains all images and radio button inputs for navigation.
- The radio buttons (`<input type="radio">`) are hidden but allow manual slide selection.
- The `.navigation` div provides labels that act as clickable slide selectors.

### **2. CSS Styling**
#### **General Styling**
```css
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #f5f5f5;
}
.carousel {
    position: relative;
    width: 80%;
    max-width: 600px;
    overflow: hidden;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}
```
**Explanation:**
- `box-sizing: border-box;` ensures padding/margins do not affect element size.
- `display: flex;` centers the carousel.
- `overflow: hidden;` hides overflowing slides, keeping only one visible at a time.

#### **Slides Layout**
```css
.slides {
    display: flex;
    width: 400%;
    animation: slide 12s infinite;
}
.slide {
    width: 100%;
    flex: 1 0 100%;
}
.slide img {
    width: 100%;
    display: block;
}
```
**Explanation:**
- `.slides` is a flex container, allowing horizontal slide layout.
- `width: 400%;` ensures all slides are placed in a single row.
- `flex: 1 0 100%;` makes each slide occupy full width.

#### **Automatic Sliding**
```css
@keyframes slide {
    0%, 25% { transform: translateX(0%); }
    30%, 50% { transform: translateX(-100%); }
    55%, 75% { transform: translateX(-200%); }
}
```
The `@keyframes slide` rule defines a CSS animation that moves the `.slides` container to create the sliding effect. Here's a breakdown of how it works:

### **Understanding Keyframes**
- `@keyframes` allows you to define animations that change CSS properties over time.
- It consists of keyframe selectors (`0%`, `25%`, etc.) that define the state of the element at different points in the animation.

### **How This Animation Works**
1. **Initial State (`0%`, `25%`)**  
   - `transform: translateX(0%);`  
   - This means the first slide is fully visible, and no movement occurs.

2. **First Slide Transition (`30%`, `50%`)**  
   - `transform: translateX(-100%);`  
   - The `.slides` container shifts left by `-100%`, bringing the second slide into view.

3. **Second Slide Transition (`55%`, `75%`)**  
   - `transform: translateX(-200%);`  
   - Moves further left, bringing the third slide into view.

4. **Third Slide Transition (`80%`, `100%`)**  
   - `transform: translateX(-300%);`  
   - Moves further left, displaying the fourth slide.

5. **Looping Behavior**
   - Since this animation is applied to `.slides` with `animation: slide 12s infinite;`, it repeats every **12 seconds** continuously.

### **Key Takeaways**
- The animation runs **infinitely** with a **12-second duration**.
- It smoothly transitions between slides at **different time intervals**.
- The `translateX()` moves the entire `.slides` container **horizontally**.

#### **Manual Navigation (Radio Buttons & Labels)**
```css
.navigation {
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
}
.navigation label {
    width: 12px;
    height: 12px;
    margin: 5px;
    background: white;
    border-radius: 50%;
    cursor: pointer;
    transition: 0.3s;
}
.navigation label:hover {
    background: #777;
}
```
**Explanation:**
- `.navigation` centers clickable dots at the bottom.
- `label` elements act as slide selectors.
- `border-radius: 50%;` makes them circular.
- `cursor: pointer;` makes them clickable.
- `transition: 0.3s;` provides a smooth hover effect.
