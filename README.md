# Week 6: Creative Code & Games

**Instructor:** Jing 

---

## Learning Objectives

- Write p5.js code to create generative, interactive visual sketches
- Understand randomness and the draw loop as creative tools
- Build a complete interactive space using Bitsy's constraints
- Articulate how limitations shape creative decisions

---

## Introduction

This week you will make two things: a visual sketch that runs in the browser, and a tiny pixel-art game. Neither requires prior coding experience — just a willingness to change a number and see what happens.

- **p5.js** is a JavaScript library for drawing on a canvas. You write a few lines, hit play, and something appears. Change a number — the shape moves. Add `random()` — it changes every time.
- **Bitsy** is a miniature game editor. You draw rooms pixel by pixel, write dialogue, and connect spaces. Two colors per room. Everything fits in a grid.


---

## Session 1 (Day 1): p5.js — Generative Visuals

### Experience first

Before writing code, look at what people make with p5.js:

- [OpenProcessing](https://openprocessing.org) — large community gallery; click any sketch to see the code, then fork it to edit your own copy
- [Zach Lieberman's daily sketches](https://www.instagram.com/zach.lieberman/) — visual experiments, posted daily for years
- [Generative Artistry tutorials](https://generativeartistry.com/) — step-by-step recreations of famous generative artworks; see how simple rules produce complex images
- [p5.js showcase](https://p5js.org/examples/) — community examples ranging from data art to interactive poetry

**As you look:** What rule might produce that image? How many lines of code do you think it took?

### How p5.js works

Open the editor at [editor.p5js.org](https://editor.p5js.org) — no account needed, but creating a free account lets you save your work.

p5.js has two core functions:

```javascript
function setup() {
  // runs once when the sketch starts
  createCanvas(400, 400);
}

function draw() {
  // runs 60 times per second, forever
  background(220);
  circle(200, 200, 50);
}
```

The `draw()` loop is the engine — everything drawn inside it redraws constantly. Add `random()` to any number and it changes every frame.

### Key functions

| Function | What it does | Example |
|----------|-------------|---------|
| `createCanvas(w, h)` | Sets canvas size in pixels | `createCanvas(600, 400)` |
| `background(r, g, b)` | Fills background with color | `background(20, 20, 40)` |
| `fill(r, g, b)` | Sets fill color for next shape | `fill(255, 100, 0)` |
| `noFill()` | Shapes have no fill | `noFill()` |
| `stroke(r, g, b)` | Sets outline color | `stroke(255)` |
| `noStroke()` | Shapes have no outline | `noStroke()` |
| `circle(x, y, d)` | Draws a circle | `circle(200, 200, 80)` |
| `rect(x, y, w, h)` | Draws a rectangle | `rect(10, 10, 100, 50)` |
| `line(x1, y1, x2, y2)` | Draws a line | `line(0, 0, 400, 400)` |
| `text(str, x, y)` | Draws text | `text("hello", 50, 200)` |
| `random(min, max)` | Returns a random number | `random(0, 400)` |
| `mouseX`, `mouseY` | Current mouse position | `circle(mouseX, mouseY, 30)` |
| `mousePressed()` | Runs when mouse is clicked | `function mousePressed() {...}` |
| `noLoop()` | Stops the draw loop | after `setup()` |
| `redraw()` | Runs draw() once manually | inside `mousePressed()` |

### Starter sketch — visual poem generator

Copy this into the editor and run it. Click the canvas to regenerate.

```javascript
let words = ["archive", "signal", "membrane", "drift", "index", "witness", "fold"];
let colors = ["#FF6B6B", "#4ECDC4", "#45B7D1", "#96CEB4", "#FFEAA7", "#DDA0DD"];

function setup() {
  createCanvas(600, 400);
  textFont("Georgia");
  textSize(36);
  noLoop();
}

function draw() {
  background(20);
  for (let i = 0; i < 8; i++) {
    fill(random(colors));
    noStroke();
    text(random(words), random(20, 550), random(40, 380));
  }
}

function mousePressed() {
  redraw();
}
```

**Now modify it:** Change the word list. Change the colors. Change the font size. Change what shape appears instead of text. Each change is a creative decision.

### In-class activity

Build a sketch with a clear concept — something you could describe in one sentence. Choose one of the prompts below or invent your own:

- *A sky that changes mood* — background color shifts based on mouse position or over time
- *A portrait made of words* — words placed at specific positions to suggest a face or figure
- *A window that shows different things at different times of day* — use `hour()` to change what appears

See **[INCLASS-ACTIVITY-P5.md](INCLASS-ACTIVITY-P5.md)** for starter code and hints for each prompt.

---

## Session 2 (Day 2): Bitsy — Space as Narrative

### Experience first

Play one or two Bitsy games before building your own:

- [*Endless Scroll*](https://haraiva.itch.io/endless-scroll) by Cecile Richard — it's a game about high school memories, growth and being online late at night
- [*Hawk & Puma*](https://nieblagames.itch.io/hawk-and-puma) by Nico Valdivia Hennig (UCR student) — it explores themes of racism, sovereignty, and religion from decolonial aesthetics and Andean-inspired music
- Browse the [Bitsy Essay Jam entries](https://itch.io/jam/the-bitsy-essay-jam/entries) — Bitsy works used as essays and arguments, not just games
- Browse [Bitsy games on itch.io](https://itch.io/games/made-with-bitsy) — hundreds of examples; sort by Top Rated

**As you play:** How does the maker use the pixel grid? What can't they show — and how do they work around it? Where does the story live — in the visuals or the dialogue? Could this have been a written essay instead — and what would be lost?

### How Bitsy works

Open the editor at [bitsy.org](https://bitsy.org) — no account needed.

| Element | What it is | How to add |
|---------|-----------|------------|
| **Avatar** | The character the player controls | Edit > Avatar |
| **Rooms** | Spaces the player moves through | Room panel > + |
| **Tiles** | Pixels that make up walls and floors | Tile panel > draw |
| **Sprites** | Characters/objects with dialogue | Sprite panel > + |
| **Items** | Things the player can pick up | Item panel > + |
| **Exits** | Doors between rooms | Room > Add exit |
| **Endings** | Text shown when player touches an ending tile | Room > Add ending |

**Basic workflow:**
1. Draw your avatar (8×8 pixel grid)
2. Draw your first room — tiles for walls, floor color
3. Add a sprite with dialogue (double-click sprite to add text)
4. Add an exit to a second room
5. Repeat for additional rooms
6. Add an ending in the final room

### In-class activity

Build a Bitsy game with 3 rooms and a clear sense of journey — beginning, middle, somewhere to arrive. The story can be abstract: a mood, a memory, a question. Each room's pixel arrangement and dialogue is a design decision.

**Export:** Game > Download game → saves as `.html` — runs in any browser.

---

## Resources

### Tools
- [p5.js Web Editor](https://editor.p5js.org) — browser-based, no install
- [p5.js Reference](https://p5js.org/reference/) — every function with examples
- [The Coding Train](https://thecodingtrain.com/tracks/code-programming-with-p5-js) — Daniel Shiffman's p5.js video tutorials; clear, enthusiastic, very beginner-friendly
- [Bitsy Editor](https://bitsy.org) — browser-based, no install; click "Make"

### Examples to Explore
- [Generative Artistry](https://generativeartistry.com/) — step-by-step generative art tutorials with p5.js
- [p5.js Showcase](https://p5js.org/showcase/) — community work
- [Bitsy games on itch.io](https://itch.io/games/made-with-bitsy) — hundreds of examples
- [Bitsy Essay Jam entries](https://itch.io/jam/the-bitsy-essay-jam/entries) — Bitsy as essay and argument
- [OpenProcessing](https://openprocessing.org) — p5.js community gallery with forkable code
- [Zach Lieberman sketches](https://www.instagram.com/zach.lieberman/) — daily creative coding practice

### Further Reading
- Emily Johnson & Anastasia Salter, *Critical Making in the Age of AI* — on making as a form of critical thinking; [the "Game" chapter](https://www.fulcrum.org/concern/monographs/zc77ss95p) is directly relevant


---

## Assignment

See [ASSIGNMENT.md](ASSIGNMENT.md) for full requirements, options, and the reflection prompt.
