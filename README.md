# Unlock Me - auto solver
![68747470733a2f2f6e6976656e742e6769746875622e696f2f696d616765732f626c6f672f756e626c6f636b2d6d652f70726f672e676966](https://github.com/galax19ksh/Unblock-Me-Puzzle/assets/112553872/6f29294c-3d28-4a32-99ff-f4efc8e8bcb6)
This project takes image or text(look at .puz files for reference) file of an Unblock Me puzzle, and then provides a step-by-step solution of the puzzle.

## The idea 
My plan was to find solutions to the puzzle using a standard graph traversal algorithm like A* . The program would keep track of several potential solutions to a puzzle at once, and explore the ones that look the most promising. Using A* as opposed to something like depth-first search would guarantee that the solution found in the end was optimal without being much more complicated to implement, so it seemed like an obvious search.

## Approach
* Using hardcorded locations relies on knowing the exact pixel locations of tile centers and borders in the image. It works only for images from a specific source, so not feasible always.
* Implementing Region detection and sampling would be more flexible and efficient. This method first identifies the game area within the image.
* It then crops and resizes the image to a standard size (600x600).
* With a known image size, potential locations of tiles and borders are hardcoded.
* The program samples pixels at these locations to determine the layout of the puzzle.
* This method allows loading puzzles from images of varying quality, not just screenshots.
