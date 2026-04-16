# In-Class Activity: p5.js Sketch Prompts

Pick **one** of the three prompts below. Use the starter code as your base — paste it into the [p5.js editor](https://editor.p5js.org), get it running, then modify from there. You do not need to understand every line before you start changing things.

---

## Prompt 1: A Sky That Changes Mood

The background color shifts depending on where the mouse is on the canvas — left feels different from right, top from bottom.

**Starter code:**
```javascript
function setup() {
  createCanvas(600, 400);
}

function draw() {
  // mouseX goes from 0 (left) to 600 (right)
  // map() converts that range to a color range
  let r = map(mouseX, 0, width, 20, 200);
  let b = map(mouseY, 0, height, 200, 20);
  background(r, 40, b);

  // a sun — try changing its size, color, and position
  noStroke();
  fill(255, 220, 100, 180);
  circle(width / 2, 80, 60);
}
```

**`map(value, start1, stop1, start2, stop2)`** converts a number from one range to another. `map(mouseX, 0, width, 20, 200)` means: when mouseX is 0 return 20; when mouseX equals the canvas width return 200; everything in between scales proportionally.

**Try changing:**
- The color values to shift the mood differently — cooler, warmer, more dramatic
- The sun's size, color, or opacity (the 4th number in `fill`)
- Add clouds: `fill(255, 255, 255, 100); rect(x, y, 80, 30);`
- Add words that describe the mood: `fill(255); text("heavy", 50, 200);`

---

## Prompt 2: A Portrait Made of Words

Words placed at specific positions suggest a face — eyes, a mouth, a shape. Nothing needs to look realistic.

**Starter code:**
```javascript
let eyeWords  = ["see", "look", "watch", "blink"];
let mouthWords = ["speak", "quiet", "wait", "hum"];

function setup() {
  createCanvas(400, 500);
  textAlign(CENTER, CENTER);
  noLoop();
}

function draw() {
  background(240);
  textFont("Georgia");

  // head outline
  noFill();
  stroke(40);
  ellipse(200, 240, 220, 280);

  // left eye
  noStroke();
  fill(40);
  textSize(18);
  text(random(eyeWords), 140, 180);

  // right eye
  text(random(eyeWords), 260, 180);

  // mouth
  textSize(14);
  text(random(mouthWords), 200, 310);
}

function mousePressed() {
  redraw();
}
```

**Try changing:**
- The words in each list — make them more specific, stranger, or personal
- Add more features: a nose (`text("breathe", 200, 250)`), eyebrows, ears
- Change `textSize()` per feature — bigger eyes, smaller mouth
- Remove the ellipse outline and let the words alone suggest the shape

---

## Prompt 3: A Window That Shows Different Things at Different Times of Day

`hour()` returns the current hour (0–23). Use it to change what appears on screen depending on when someone opens the sketch.

**Starter code:**
```javascript
function setup() {
  createCanvas(500, 400);
  noLoop(); // draw once — the time does not change mid-session
}

function draw() {
  let h = hour();

  if (h >= 6 && h < 12) {
    // morning
    background(255, 220, 150);
    fill(255, 180, 0);
    circle(250, 80, 80);
    fill(60); textSize(24);
    text("morning", 220, 220);

  } else if (h >= 12 && h < 18) {
    // afternoon
    background(135, 206, 235);
    fill(255, 255, 255, 180);
    circle(300, 100, 60);
    fill(60); textSize(24);
    text("afternoon", 200, 220);

  } else if (h >= 18 && h < 22) {
    // evening
    background(255, 120, 60);
    fill(200, 80, 0);
    circle(250, 350, 100);
    fill(255); textSize(24);
    text("evening", 220, 180);

  } else {
    // night
    background(10, 10, 40);
    fill(255, 255, 200);
    circle(350, 80, 50);
    fill(255); textSize(24);
    text("night", 230, 220);
  }
}
```

**Try changing:**
- The colors for each time of day
- What appears — add stars at night (`circle(random(500), random(400), 3)`), add rain in the afternoon
- What the text says — make it a feeling, a question, a sound instead of a time label
- Add a second element to each scene

---

## General Tips

- **Run first, understand later.** Paste the code, hit play, see what it does — then start changing numbers.
- **One change at a time.** Change one value, run it, see what happened. This is how everyone codes.
- **Breaking it is fine.** If the sketch stops working, undo (Cmd+Z / Ctrl+Z) and try a smaller change.
- **Save your work.** Create a free account at [editor.p5js.org](https://editor.p5js.org) so your sketch is saved automatically.
