## README.md

# SortViz

**SortViz** is a visual learning tool designed to demystify how sorting algorithms function. By transforming abstract code into a synchronized visual performance, it allows users to compare the efficiency and behavior of different sorting techniques side-by-side.

URL - https://sand-tetris-jrgz.vercel.app/

## 🚀 Features
* **Multiple Algorithms:** Visualizations for Bubble Sort, Selection Sort, Insertion Sort, Merge Sort, and Quick Sort.
* **Visual Indicators:** Uses distinct color coding to represent different array states:
    * **Default:** Unsorted elements.
    * **Comparing:** Elements currently being evaluated.
    * **Swapping:** Elements changing positions.
    * **Sorted:** Elements in their final, correct position.
* **Control Panel:** Adjustable animation speed and array size to observe performance scaling.
* **Responsive Bars:** Dynamic scaling of visual bars based on the viewport and data volume.

## 🛠️ Technical Stack
* **JavaScript (ES6):** Implementation of sorting algorithms using `async/await` and `Promises` to control animation timing.
* **HTML5:** Semantic structure for the visualization container.
* **CSS3:** Flexbox-based layout for the bars and smooth transitions.

## 🕹️ How to Use
1. **Clone the repository:**
   ```bash
   git clone https://github.com/HenitJain/SortViz.git
   ```
2. **Launch:**
   * Open `index.html` in your browser.
3. **Execution:**
   * Click **Generate New Array** to randomize the data.
   * Select an algorithm from the menu.
   * Click **Sort** to watch the process in real-time.

## 📂 Project Structure
* `index.html`: The visualization stage and UI controls.
* `sort.js`: The central logic for handling animation delays and DOM updates.
* `algorithms/`: Individual files for each sorting logic (e.g., `bubbleSort.js`, `quickSort.js`).
* `README.md`: Documentation.

## ⚙️ Logic: Asynchronous Visuals
The primary challenge in a JavaScript visualizer is preventing the browser from "freezing" during long loops. This project solves this using a custom `sleep` function:

```javascript
const sleep = (ms) => new Promise(resolve => setTimeout(resolve, ms));

async function bubbleSort(array) {
    for (let i = 0; i < array.length; i++) {
        for (let j = 0; j < array.length - i - 1; j++) {
            // Highlight bars...
            await sleep(speed); 
            // Swap and update DOM...
        }
    }
}
```
This allows the browser to render the "Comparing" and "Swapping" states at every step, making the algorithm's time complexity visible to the naked eye.
