# Viability Report & Implementation Guide

You asked which of the designs (3, 4, 6, 7) is **"more viable"** and can be done **"easily using simple HTML code"**.

## The Verdict: Example #6 (Pennsylvania Western University Style)

**Why?**
The **"Card Layout"** combined with a **"Parallax Hero"** is the clear winner for three reasons:
1.  **Direct Replacement for Tables:** You currently have data (Course, Description, Fee) in a table. Tables are hard to make responsive on phones. "Cards" (divs) are the industry standard for this data and are incredibly easy to stack on mobile using CSS Grid.
2.  **High Impact / Low Effort:** The "Parallax" effect (where the background stays fixed while you scroll) looks very professional but only requires **one single line of CSS**: `background-attachment: fixed;`.
3.  **No Advanced Skills Needed:** You don't need complex clip-paths (like Example 4) or JavaScript logic (like Example 7's search bar).

### Comparison of Difficulty

| Style | Key Feature | HTML/CSS Difficulty | Verdict |
| :--- | :--- | :--- | :--- |
| **#6 PennWest** | **Parallax & Cards** | **Low (Easiest)** | **Best Choice.** High visual impact, easy code. |
| **#7 CBU** | Split Screen | Low | Good alternative, but less impressive than Parallax. |
| **#3 MTU** | Sticky Nav | Low-Medium | Good utility, but visually "safe". |
| **#4 Aquinas** | Wavy Shapes | High | Requires SVG knowledge; too hard for a simple prototype. |

---

## How to Use the Provided Prototype

I have created a file `simple_prototype.html` for you. It uses the content from your PQR images but applies the **PennWest Style**.

### Key Code Features I Used:

1.  **The Parallax Hero (`.hero`)**
    ```css
    background-attachment: fixed; /* This does the magic! */
    background-size: cover;
    ```
    This single rule makes the background image stay still while the text scrolls over it, creating depth.

2.  **The Card Grid (`.grid-container`)**
    ```css
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    ```
    This replaces your table. It tells the browser: "Fit as many 280px-wide cards as you can in the row. If the screen is smaller, stack them." **No media queries needed!**

3.  **Sticky Header (`header`)**
    ```css
    position: sticky;
    top: 0;
    ```
    This keeps your navigation bar visible at the top of the screen even when the user scrolls down (borrowed from Example #3).

### Instructions
1.  Open `simple_prototype.html` in your browser to see the result.
2.  Replace the image URL in the CSS (`background-image`) with a photo of your actual college building.
3.  Edit the text in the `<div class="card">` sections to match your exact course details.
