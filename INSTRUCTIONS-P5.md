# Step-by-Step: Building a p5.js Sketch

**Time needed:** 45–60 minutes | **No downloads required**

---

## What is p5.js?

p5.js is a JavaScript library for creative coding. You write code in a browser-based editor and it draws shapes, colors, text, and animations on a canvas. No installation, no setup — just open the editor and start writing.

Everything you make can be shared with a link.

---

## Step 1: Open the Editor

Go to [editor.p5js.org](https://editor.p5js.org).

You will see code already in the editor:

```javascript
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}
```

Click the **Play button (▶)** to run it. You will see a gray square — that is your canvas.

---

## Step 2: Understand the Two Functions

**`setup()`** runs **once** when your sketch starts. Use it to set the canvas size and any one-time settings.

**`draw()`** runs **60 times per second**, forever. Everything you draw inside it redraws constantly. This is how animation works.

---

## Step 3: Draw Something

Add a circle inside `draw()`:

```javascript
function draw() {
  background(220);
  circle(200, 200, 80);
}
```

- `200, 200` = center position (x, y) — measured from the top-left corner
- `80` = diameter in pixels

Click Play. You should see a white circle on a gray background.

---

## Step 4: Add Color

Use `fill()` before a shape to set its color. Colors are RGB (red, green, blue), each 0–255:

```javascript
function draw() {
  background(20, 20, 40);      // dark blue-gray background
  fill(255, 100, 0);           // orange fill
  noStroke();                  // no outline
  circle(200, 200, 80);
}
```

---

## Step 5: Add Randomness

`random(min, max)` returns a different number every time it runs. Put it inside `draw()` and values change every frame:

```javascript
function draw() {
  background(20, 20, 40);
  fill(random(255), random(255), random(255));
  noStroke();
  circle(random(400), random(400), random(20, 80));
}
```

This draws a randomly placed, randomly colored, randomly sized circle 60 times per second. It will feel chaotic — that is a starting point, not a finished piece.

---

## Step 6: Control the Loop

To make your sketch **static** (draws once, then stops), use `noLoop()` in setup:

```javascript
function setup() {
  createCanvas(600, 400);
  noLoop();
}

function draw() {
  // draws once
  background(20);
  for (let i = 0; i < 100; i++) {
    fill(random(255), random(255), random(255), 150);
    noStroke();
    circle(random(600), random(400), random(10, 60));
  }
}
```

To **redraw on click**, add `mousePressed()`:

```javascript
function mousePressed() {
  redraw();  // runs draw() one more time
}
```

---

## Step 7: Use a Loop to Draw Many Things

`for` loops let you draw many shapes at once:

```javascript
for (let i = 0; i < 50; i++) {
  circle(random(width), random(height), 20);
}
```

- `width` and `height` are built-in variables — they equal your canvas size
- Change `50` to draw more or fewer shapes

---

## Step 8: Add Text

```javascript
function draw() {
  background(20);
  fill(255);
  textSize(32);
  textAlign(CENTER, CENTER);
  text("hello", width / 2, height / 2);
}
```

You can use `random()` with text too — store words in an array and pick randomly:

```javascript
let words = ["archive", "signal", "drift", "echo"];

function draw() {
  background(20);
  fill(255);
  textSize(48);
  text(random(words), random(width), random(height));
}
```

---

## Step 9: Respond to the Mouse

`mouseX` and `mouseY` always hold the current mouse position:

```javascript
function draw() {
  background(20);
  fill(255, 100, 0);
  circle(mouseX, mouseY, 40);
}
```

---

## Step 10: Save and Share

1. Create a free account at [editor.p5js.org](https://editor.p5js.org) — required to save your work
2. Click **File > Save**
3. Click **File > Share** → copy the "Sketch" link
4. In your GitHub repo: click **"Add file"** → **"Create new file"** → name it `links.md` → paste your link → click **"Commit changes"**

---

## Common Errors

| Error message | Likely cause | Fix |
|--------------|-------------|-----|
| `is not defined` | Variable or function name is misspelled | Check spelling exactly — JavaScript is case-sensitive |
| `is not a function` | Missing parentheses or wrong name | Check the [p5 reference](https://p5js.org/reference/) for exact syntax |
| Nothing appears | `draw()` is empty or shapes are off-canvas | Make sure x/y values are within your canvas size |
| Everything flickers | `background()` is missing | Add `background(color)` as the first line of `draw()` |
| Sketch runs but canvas is white | `fill()` is white on white background | Change background or fill color |
