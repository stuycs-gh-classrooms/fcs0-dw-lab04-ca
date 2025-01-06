# Foundations of Computer Science Lab04

Your goal is to recreate this program from the sample code provided:
- <http://homer.stuy.edu/~dw/netlogo/lab04_obf.html>

### Instructions
At the end of this file, you will see a large code block. It contains some instructions and starter code for this assignment. You should:
- Copy the code block into a new NetLogo program.
- In NetLogo, fill in the procedures and add the required interface elements.
- When done, save the file as __lab04.nlogo__, and upload the entire file to this repository.

### Cellular Automata Details
You will be making a generic 2-state Cellular Automata model (often referred to a life-like CA). Your model should adhere to the criteria below:

#### General World State and Mechanics
- All patches will be either dead (black) or alive (white).
- Each round, every patch will:
  - Count the number of living neighbors it has.
  - Change state based on the number.
  - These 2 steps should be totally separate (all patches should count neighbors before any state changing).

#### State Changing Rules.
- Dead patches must turn alive if they have enough living neighbors.
- Living patches must turn dead if they have too many or not enough living neighbors.
- The specific values for birth or survival will be set by the following sliders in your model:
  - birth_min: Minimum number of living neighbors required for a dead cell to become alive.
  - birth_max: Maximum number of living neighbors required for a dead cell to become alive.
  - survive_min: Minimum number of living neighbors required for a living cell to stay alive.
  - survive_max: Maximum number of living neighbors required for a living cell to stay alive.

#### Example Rules:
Conway's Game Of Life:
- birth_min: 3
- birth_max: 3
- survive_min: 2
- survive_max: 3

Tapestry
- birth_min: 2
- birth_max: 4
- survive_min: 0
- survive_max: 0

You can find other rule sets here: <https://en.wikipedia.org/wiki/Life-like_cellular_automaton>


### Starting States
`setupGlider` (to be used with game of life rules):

| | -1 | 0 | 1 |
| -- | -- | -- | -- |
| __1__ |   |   | X |
| __0__ | X |   | X |
| __-1__ |   | X | X |

`setupSquare` (to be used with tapestry rules):

| | -1 | 0 | 1 |
| -- | -- | -- | -- |
| __1__ |   |  X | X |
| __0__ |   |  X | X |
| __-1__ |   |  |  |


### Starter Code:
```
; For this assignment, you will need to create procedures
; and interface elements.
; Use this example as your guide:
; http://homer.stuy.edu/~dw/netlogo/lab04_obf.html

;=========================================
; Buttons
;
; Most procedures should have a corresponding button.
; If the button is meant to be a forever button it
; will be mentioned above the procedure.

;=========================================
; Sliders
; density: range should be [0, 100], integers only.
;
; brith_min: range should be [0, 8], integers only.
; brith_max: range should be [0, 8], integers only.
; survive_min: range should be [0, 8], integers only.
; survive_max: range should be [0, 8], integers only.
;=========================================

; patches will need to keep track of the
; number of living neighbors, this will give all
; patches a new property called living_neighbors to
; be used for this purpose.
patches-own [living_neighbors]

;=========================================
;Procedures

;=========================================
; setupSquare (normal button)
; clear the screen
; create a 2x2 square of alive patches with the origin as the
; bottom-left corner of the square.
to setupSquare

end

;=========================================
; setupGlider (normal button)
; clear the screen
; create a glider pattern at the center of the screen.
; See README.md for the glider pattern.
to setupGlider

end

;=========================================
; setupRandom (normal button)
; clear the screen
; Every patch should have a density (slider) %
; chace of being alive.
to setup_random

end

;=========================================
; go (forever button)
; wait a small amount of time
; Run a single generation of the set cellular
; automata model. See the README.md document for details.
to go

end
```
