# 2D Farming Game

This repository contains a simple 2‑dimensional farming game implemented in **HTML**, **CSS**, and **JavaScript**. The game is designed to run in a web browser without any external libraries or frameworks.

## Features

* **Grid‑based farm:** The game area is a 6×6 grid representing plots of land. Each cell can be empty, planted, or have a fully grown crop.
* **Planting and harvesting:** Click on a plot while the **Plant Seed** action is selected to plant a seed. After a short time the crop will grow. Switch to the **Harvest** action and click on a fully grown crop to harvest it and increase your harvest count.
* **Real‑time growth:** Crops take approximately 10 seconds to grow. As time passes, planted cells automatically transition to grown crops.
* **Inventory counter:** Your harvested crop count is displayed at the top of the page and updates as you harvest crops.

## How to Run

1. Clone or download this repository.
2. Open the `index.html` file in any modern web browser (e.g., Firefox, Chrome). No additional dependencies are required.
3. Use the **Plant Seed** and **Harvest** buttons to select your current tool. Click on the grid to plant seeds or harvest crops.

## Explanation

The game uses an HTML `<canvas>` element as the primary drawing surface. The `<canvas>` element is well suited for creating web games because it provides a 2D drawing context that allows developers to draw shapes, text, and images directly via JavaScript【691042296315168†L818-L825】. A simple game loop driven by `requestAnimationFrame` updates crop growth and renders the grid at approximately 60 frames per second.

### Game Logic

* **Game state:** Two 2‑dimensional arrays store the state of each cell (`cellStates`) and the timestamp when a seed was planted (`plantTimes`). These arrays are initialized when the page loads.
* **Planting:** When the user clicks a grid cell while the **Plant Seed** action is selected, the game sets that cell’s state to `1` (planted) and records the current time in `plantTimes`.
* **Growth:** On each frame, the game checks whether the current time minus the recorded planting time exceeds the growth duration. If so, the cell state transitions to `2` (grown).
* **Harvesting:** When the user clicks a cell while the **Harvest** action is selected and that cell’s state is `2`, the game increments the player’s inventory and resets the cell’s state to `0` (empty).

## License

This game is provided as an educational example. Feel free to use, modify, and distribute it as you see fit.
