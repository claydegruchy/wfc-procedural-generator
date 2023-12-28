# WFC Prod Gen 2
A wave form collapse based map generator

# How
If you want to learn more about WFC check this out https://github.com/mxgmn/WaveFunctionCollapse 

# Making packs
Packs need to be created in two locations
1. Foundry with Token Attacher
2. `config.js`
These are outlined below.

## Foundry with Token Attacher
First, create a bunch of tiles in foundry. To do this:
- create an NPC token
- Follow the Token Attacher instructions (baileywiki guides are the go to) to adorn your token with whatever nice aspects you'd like (walls, lights, etc.).
- Ensure you give the token a clear verical and horizonal points that will map up with others, this generator is going to copy these tokens a lot and if they don't like up it'll look shithouse.
- Bind a prototype from the created token (this is hard shit if you're using WFRP as the button doesn't appear in the usual place).
- Give the token a nice clear name so you can identify it later (if I was creating a set of underground dungeons, and this is a vertical corridor, I might name my token `underground-dungeon-v-1`).
- Now repeat this process for each other permutation. You'll want at least one vertical (║), one horizonal (═), a corner (╔), and an end. 

## `config.js`
Once you have your tiles, you need to add them to `config.js`.
- Copy the `wfc.registerPack("degruchy-test", {`[...]`}`
- for each tile, insert a relevant section with the sockets defined and matching up
- if you wish to have an offset, add a `centreOffset` field referening the offset between the centre of the prefab and the actual actor in the prefab
    - eg: `"centreOffset": { "x": -100, "y": -100, "z": 0 },`, if my 3x3 


## Helpers
### Open settings macro
`new (game.settings.menus.get("wfc-procedural-generator.app").type)().render(true)`

### Import a character template
`tokenAttacher.importFromJSON(<some json>)`