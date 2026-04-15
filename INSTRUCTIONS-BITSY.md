# Step-by-Step: Building a Bitsy Game

**Time needed:** 45–60 minutes | **No downloads required**

---

## What is Bitsy?

Bitsy is a tiny game editor that lives in your browser. You build pixel-art worlds using an 8×8 grid — each room is 16×16 tiles. Your avatar walks around, talks to characters, picks up items, and moves between rooms.

The constraints are the point: with only two colors per room and very basic movement, every creative decision is visible.

---

## Step 1: Open the Editor

Go to [make.bitsy.app](https://make.bitsy.app).

You will see the editor with a default room already created. The panels on the right control your tools.

---

## Step 2: Draw Your Avatar

Your avatar is the character the player controls.

1. Click **"avatar"** in the top toolbar
2. Use the 8×8 pixel grid to draw your character — click cells to fill them
3. Keep it simple: a silhouette reads better than fine detail at this scale

---

## Step 3: Set Your Room Colors

Each room has two colors: a **background** and a **tile** color.

1. Click the color swatches at the top of the room panel
2. Pick colors that feel right for your first space — dark/light contrast works best

---

## Step 4: Draw Tiles (Walls and Floors)

Tiles are the building blocks of your room — they create walls, floors, and visual texture.

1. Click **"tile"** in the toolbar
2. Draw a pattern on the 8×8 tile grid
3. In the room view (the large grid), click cells to place your tile
4. Your avatar cannot walk through tiles — use them to create walls and paths

**Tip:** Draw the walls first, then leave the middle open for the player to walk through.

---

## Step 5: Add a Sprite with Dialogue

Sprites are characters or objects in your room. They block movement and can speak when the player walks into them.

1. Click **"sprite"** in the toolbar
2. Draw your sprite on the 8×8 grid
3. Click the **dialog** tab — type what the sprite says when the player touches it
4. In the room view, click a cell to place the sprite

**Dialog formatting:**
- Just type — plain text works
- Line breaks appear naturally
- Separate screens of dialog with a blank line

---

## Step 6: Add More Rooms

1. In the **room panel** (top right), click **"+"** to add a new room
2. Each room can have different colors — change them in the palette
3. Draw new tiles and sprites in each room

---

## Step 7: Connect Rooms with Exits

Exits move the player from one room to another when they walk to a specific tile.

1. In the room you want to **leave from**, click **"exits"** in the room panel
2. Click the tile in the room grid where the exit should be
3. Choose the **destination room** and the **tile in that room** where the player arrives

**Common pattern:** Place an exit at the edge of one room, arriving at the opposite edge of the next room — creates a sense of walking through a door.

---

## Step 8: Add an Ending (Optional)

Endings show a full-screen message when the player walks onto a specific tile.

1. Click **"endings"** in the room panel
2. Click a tile in your room to place the ending
3. Type the ending text

Endings are a natural way to close a narrative — a final line of dialogue, a place name, a feeling.

---

## Step 9: Add a Title

1. Click the **"game"** tab in the top toolbar
2. Fill in your game's title and creator name
3. This appears on the title screen when the game starts

---

## Step 10: Play-Test

Click **"play"** (the triangle button in the top bar) to run your game in the editor. Walk through every room and every exit to make sure nothing is broken.

Common issues to check:
- Can the avatar reach all exits without getting stuck in tiles?
- Does every sprite have dialogue?
- Does the ending trigger correctly?

---

## Step 11: Export as HTML

When you are ready to submit:

1. Click **"game"** in the top toolbar
2. Click **"Download game"**
3. A `.html` file saves to your computer
4. Upload it to your GitHub repo — drag and drop in the web interface

The `.html` file runs in any browser. Your instructor opens it to play your game.

---

## Tips

- **Two colors only** — use the contrast intentionally. Dark rooms feel different from light ones.
- **Dialogue carries the story.** You cannot add sound or complex animation — words do the work.
- **Small is fine.** Three rooms with clear intention is better than eight rooms with nothing to say.
- **The pixel grid is expressive.** A sprite does not need to look realistic to communicate — a shape, a silhouette, an abstract form all work.
- **Stuck?** The [Bitsy Wiki](https://bitsy.fandom.com/wiki/Bitsy_Wiki) has documentation for every feature. The itch.io community is also very active and helpful.
