# The Level Editor

Every chapter added a small dev tool to the game. This is the chapter where all of that pays off. We build a full in-game tile editor: paint tiles with the mouse, place spawn points, save the map to disk, load it back. Your game becomes its own IDE.

## Design Before You Build

<!-- TODO: what the editor needs to do — paint tiles, erase tiles, place/remove spawn points,
         switch tile types, save, load, toggle between editor and play mode.
         What it doesn't need to do — everything else. Keep it minimal. -->

## Editor Mode Toggle

<!-- TODO: E key switches between gameplay and editor modes. Different input handling, no enemies in editor mode. -->

## Tile Painting

<!-- TODO: left-click paints selected tile type at cursor world position.
         Right-click erases (sets to empty).
         Mouse drag to paint while moving. -->

## Tile Palette

<!-- TODO: simple HUD palette showing available tile types.
         Number keys or click to select. Highlight selected. -->

## Spawn Point Placement

<!-- TODO: placing player start and enemy spawn markers.
         Stored separately from tile data. -->

## Save and Load

<!-- TODO: $gtk.write_file to serialize map as JSON or simple CSV.
         Load on startup if file exists, fall back to default map.
         Discuss the data format — simple is better than clever. -->

## Undo

<!-- TODO: push each edit to a history stack, Ctrl-Z pops and reverts.
         Cap history at N steps — don't let it grow forever. -->

## Dev Tool: This Chapter _is_ the Dev Tool

<!-- TODO: meta-note — the entire editor is the dev tool. Tie back to the thread running through the book.
         Using the minimap from ch6 in the editor to navigate. Using the entity counter from ch4.
         All the pieces fit together. -->

## Extra Credit

<!-- TODO: copy/paste rectangular regions, grid snap for entity placement, multi-layer maps -->

## Summary

<!-- TODO -->

## What's Next

One chapter left. Let's ship it.
