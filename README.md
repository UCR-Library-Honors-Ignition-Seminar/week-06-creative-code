# Week 6: Creative Code & Games

**Instructor:** Jing | **Weeks 5–8 format:** Critical/Creative Reflection

---

## Learning Objectives

- Write p5.js code to create generative, interactive visual sketches
- Understand randomness and the draw loop as creative tools
- Build a complete interactive space using Bitsy's constraints
- Articulate how limitations shape creative decisions

---

## Background: Code as a Design Material

Most people think of code as a means to an end — a way to make software do something useful. Creative coding flips this: **the code itself is the design material.** A loop that draws 200 circles is a compositional decision. A random number is an aesthetic choice. Writing `random(width)` is the same kind of move as scattering seeds on paper.

This week you will work with two tools that sit at opposite ends of a spectrum:

- **p5.js** gives you a blank canvas and nearly unlimited possibility — you decide what exists and what moves
- **Bitsy** gives you almost nothing — a tiny pixel grid, two colors, basic movement — and that scarcity becomes the work

The question both tools ask: *what do you make when the tool decides some things for you?*

---

## Session 1 (Day 1): p5.js — Generative Visuals

### Experience first

Before writing code, look at what people make with p5.js:

- [Zach Lieberman's daily sketches](https://www.instagram.com/zach.lieberman/) — visual experiments, posted daily for years
- [Generative Artistry tutorials](https://generativeartistry.com/) — step-by-step recreations of famous generative artworks; see how simple rules produce complex images
- [p5.js showcase](https://p5js.org/showcase/) — community examples ranging from data art to interactive poetry

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

Build a sketch with a clear concept — not just "random shapes," but something you could describe in one sentence: *"a sky that changes mood," "a portrait made of words," "a clock that lies."* Use the starter as a base or start from scratch.

---

## Session 2 (Day 2): Bitsy — Space as Narrative

### Experience first

Play one or two Bitsy games before building your own:

- [*A Fortune-Telling Machine*](https://witchpunx.itch.io/fortune) — a quiet Bitsy piece about prediction and uncertainty
- [*Mirror Lake*](https://sophieh.itch.io/mirror-lake) — uses Bitsy's tiny world to create atmosphere
- Browse [Bitsy games on itch.io](https://itch.io/games/made-with-bitsy) — filter by "Made with Bitsy"; sort by Top Rated

**As you play:** How does the maker use the pixel grid? What can't they show — and how do they work around it? Where does the story live — in the visuals or the dialogue?

### How Bitsy works

Open the editor at [make.bitsy.app](https://make.bitsy.app) — no account needed.

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
- [Bitsy Editor](https://make.bitsy.app) — browser-based, no install
- [Bitsy Wiki](https://bitsy.fandom.com/wiki/Bitsy_Wiki) — community documentation

### Examples to Explore
- [Generative Artistry](https://generativeartistry.com/) — step-by-step generative art tutorials with p5.js
- [p5.js Showcase](https://p5js.org/showcase/) — community work
- [Bitsy games on itch.io](https://itch.io/games/made-with-bitsy) — hundreds of examples
- [Zach Lieberman sketches](https://www.instagram.com/zach.lieberman/) — daily creative coding practice

### Further Reading
- [*10 PRINT CHR$*](https://10print.org/) — a book about a single line of BASIC code and what it reveals about creativity, randomness, and culture (free PDF)
- Anna Anthropy, [*Rise of the Videogame Zinesters*](https://www.goodreads.com/book/show/12876590-rise-of-the-videogame-zinesters) — on personal games and small tools as creative practice

---

## Assignment

See [ASSIGNMENT.md](ASSIGNMENT.md) for full requirements, options, and the reflection prompt.
