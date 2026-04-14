# Week 6: Creative Code & Games

**Instructor:** Jing

---

## Learning Objectives

- Write basic p5.js code to create generative visual sketches
- Understand randomness and repetition as creative tools
- Build a complete interactive space using Bitsy's constraints
- Articulate the relationship between constraint and creative freedom

---

## Introduction: Code as a Design Material

Most people think of code as a means to an end. Creative coding flips this: the code itself is the design material. Loops, random numbers, rules that say "draw 50 circles here" — these are compositional decisions, like brushstrokes.

**Constraints don't limit creativity — they direct it.** Bitsy gives you a tiny grid, two colors, and very basic movement. These restrictions mean every pixel counts.

---

## Session 1 (Day 1): p5.js — Generative Visuals

Browser-based, no account needed: [editor.p5js.org](https://editor.p5js.org)

### Core concepts

```javascript
function setup() {
  createCanvas(400, 400);
}
function draw() {
  background(220);
  let x = random(width);
  let y = random(height);
  circle(x, y, 50);
}
```

Key functions: `random()`, `circle()`, `fill(r,g,b)`, `noLoop()`, `redraw()`

**Starter code — visual poem generator:**
```javascript
let words = ["archive", "signal", "membrane", "drift", "index"];
let colors = ["#FF6B6B", "#4ECDC4", "#45B7D1", "#96CEB4", "#FFEAA7"];

function setup() {
  createCanvas(600, 400);
  textFont('Georgia');
  noLoop();
}
function draw() {
  background(20);
  textSize(32);
  fill(random(colors));
  text(random(words), random(50, 550), random(50, 350));
}
function mousePressed() { redraw(); }
```

---

## Session 2 (Day 2): Bitsy — Space as Narrative

Browser-based, no account: [make.bitsy.app](https://make.bitsy.app)

### Core concepts
| Element | What it is |
|---------|-----------|
| **Rooms** | Spaces your avatar moves through |
| **Sprites** | Static objects with optional dialogue |
| **Items** | Objects the player can pick up |
| **Exits** | Connections between rooms |

**In-class activity:** Build a Bitsy game with 3 rooms and at least 1 dialogue sprite.

**Export:** File > Download game > saves as HTML

---

## Resources

- p5.js editor: [editor.p5js.org](https://editor.p5js.org) | Reference: [p5js.org/reference](https://p5js.org/reference/)
- The Coding Train (p5.js tutorials): [thecodingtrain.com](https://thecodingtrain.com)
- Bitsy: [make.bitsy.app](https://make.bitsy.app) | Wiki: [bitsy.fandom.com](https://bitsy.fandom.com/wiki/Bitsy_Wiki)

## Project & Assignment

See [ASSIGNMENT.md](ASSIGNMENT.md) for full requirements.
