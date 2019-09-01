### From wikipedia:

Backgammon is one of the oldest known board games. Its history can be traced back nearly 5,000 years to archeological discoveries in Mesopotamia.[1][2][3][4] It is a two player game where each player has fifteen pieces (checkers) which move between twenty-four triangles (points) according to the roll of two dice. The objective of the game is to be first to bear off, i.e. move all fifteen checkers off the board. Backgammon is a member of the tables family, one of the oldest classes of board games.

Backgammon involves a combination of strategy and luck (from rolling dice). While the dice may determine the outcome of a single game, the better player will accumulate the better record over series of many games, somewhat like poker.[5] With each roll of the dice, players must choose from numerous options for moving their checkers and anticipate possible counter-moves by the opponent. The optional use of a doubling cube allows players to raise the stakes during the game.

### Description.

This repository contains all code related to this application, handling both backend & frontend code. Application itself is created for learning purposes & should not be treated as competitor for any existing solution. More likely, that it never will be published anywhere except of github pages or y.voychuk.com domain.

### Tech stack.

#### Backend
- database: postrges
- backend lang: javascript
- web-server: express

#### Frontend(~)
- framework/library: vuejs
- static typing: typescript
- testing: jest + mocha
- helper library: lodash
- styles: css-in-js
- components: based on material
- bundler: webpack

### Requirements (in order of importance):
- store gamers accounts and games history
- allow game session between 2 players on 1 pc
- allow game session betweeb 2 players on different machines
- show stats & history
- implement different game types
- allow settings for skins, game rules, etc.
- implement chatting
- create mobile app
- create desktop app

### Tech overview
#### Database architecture.
##### User model.
Standard user model with specific extra fields, like level, stats, etc.
`{  
  id: string,  
  name: string,  
  email: string,  
  password: string, // is it secure?  
  level: string,  
  stats: {  
    wins: number,  
    losses: number,  
  },  
  isPlaying: boolean,  
  isActive: boolean,  
}`

##### Game model.
Store information about game session.
`{  
  id: string,  
  name: string,  
  players: list[string],  
  isActive: boolean,  
  winner: string,  
  stats: StatsModel,  
}`

##### Stats model.
This should store different specific fields, like number of tuples, speed of players, etc.
TBD (after game session).

### WebServer overview.
Express server will be used for this purposes with corresponding plugins for requests, etc. This part will be specified more after development.

### Frontend overview.
This part of the app might change heavily due to interest in different technologies. For example it is not final decision to use vue or typescript in favor of reasonml or clojurescript or anything else. This part will be described later after backend pre-alpha will be ready.

### Repository structure.
Monorepo structure will be used, so that appropriate tools will be used for this purposes. Yarn workspaces will be used to manage monorepo. Generally it will be divided into backend & frontend parts.
Approximate structure will look like this:
- backend   
  ...
- frontend  
  ...

### Versioning.
FE & BE parts will have different version rythm, but inside of them everything should have same version. For compatibility reasons, both FE & BE should know whether its version is compatible with each other.

### Work plan.
1. Prototype of browser-only single-machine game.
2. TODO.

### Release dates.
Alpha version must be released before December 1st, 2019.
