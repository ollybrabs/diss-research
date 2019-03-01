# diss-research
JavaScript visualisations for my dissertation based around procedural content generation

## delaunayTriangulation.html
Contains a JavaScript implementation of Delaunay Triangulation, using Prim's algorithm to find the minimum spanning tree (MST). The generated MST is updated in realtime as points are moved.

### Example output
![Delaunay sample](/samples/delaunaysample.PNG)


## DungeonGenerator.html
Contains a JavaScript implementation for the methods used in the dungeon generator. Various parameters can be changed to influence the outcome of the generator:

* Room dimensions: Influence how small or large rooms are, and the variance between the lower and upper bounds of room sizes
* Coverage wanted: Given as a percentage (0.0 - 1.0), the generator aims to fill this percentage of the grid with room cells
* Room padding: The minimum spacing between rooms on the grid. Eg - 1 for 1 cell of empty space between rooms
* Chance to restore edges: Given as a percentage (0.0 - 1.0), adds edges that aren't a part of the MST back, which can result in more believable corridors between rooms
* Mean ratio: Rooms that are smaller than the mean size of rooms * **mean ratio** are deleted (but can be reactivated when a corridor passes through them). A mean ratio value of 0.0 would result in no rooms being deleted

### Example output (low coverage, high mean ratio)
![Low coverage](/samples/generator1.PNG)

### Example output (high coverage, lower mean ratio)
![High coverage](/samples/generator2.PNG)

### Example output (high coverage, lower mean ratio, debug settings)
![High coverage with debug](/samples/generator3.PNG)

## Early C# Unity implementation
* Fully tileable dungeons
* Corridors generated using a C# implementation of the A* search algorithm on a randomly weighted grid of cells
![Unity implementation](/samples/unitysample1.PNG)
![Unity implementation GIF](/samples/project5.gif)
