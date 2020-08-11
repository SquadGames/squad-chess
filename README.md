# SquadChess

An example moddable chess variant built on Squad Games.

Squad Chess implements a configration schema for defining Components
(chess pieces) and Formats (boards and starting positions) allowing
contributors (modders) to create and publish new chess variants. It's
built on the Squad Games platform so contributors own their work and
can earn crypto-currency from their success.

The UI has forms for creating contributions.

## Piece Component Configuration

Pieces are implemented by selecting and configuring mechanics that the
game has implemented. For example a Pawn, among other mechanics, can
`move` straight ahead and `capture` diagonally ahead.

Each mechanic takes some configuration data. Both `move` and `capture`
are configured by listing the offsets and number of steps allowed,
though they are interpreted by the game differently.

So a Pawn, in part, is defined this way. The full schema is defined
(here)[TODO]

```
...
mechanics: {
  move: [
    { offset: [0, 1], steps: 1 }
  ],
  capture: [
    { offset: [1, 1], steps: 1 },
    { offset: [-1, 1], steps: 1 }
  ]
}
...
```

## Board and Starting Position Format Configuration

All pieces contributed by the community are available to include in
new Formats according to licensing rules chosen by their contributors
(covered here)[TODO]. Formats list their name, the Pieces in the
format, and the starting game state.

```
{
  "name": String,
  "components": [Id],
  "data": {
    "stratingPosition": {SquareCoordinates: null | {
      "peiceId": Id,
      "player": 0 | 1,
      ...
    }},
  }
}
```

## Licenses

Squad Chess uses the standard (Squad Games licenses)[TODO].

* The game itself
  * Free play mode
  * Multiplayer mode
* Format and Component data schemas
* Contribution Interface
* Multiplayer Lobby
* Format Browser
