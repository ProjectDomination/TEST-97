# TEST-97
## The Baseland of Game Maker 8.0 Experimental Project Files

This is a repository for Test files used for experimentation, testing, and as useful resources.

## List of Project Files
### ID 102614833 - movetest.gmk
movetest is a test game created to test a new bullet movement code, creating two variations of bullet movement: gradually accelerating speed and slow decreasing speed with accelerating speed after it stops moving. movetest.gmk has two rooms, where *room1* shows the first variation, and *room0* shows the second variation.

This bullet movement code was used for Rejected Domination: Eternal Equinox (RD-1).

### ID ID 892793336 - THScoreSys (thscoresys.gmk)
THScoreSys is a test game created to showcase a new way to simulate one of the parts of Touhou's scoring system: Point Item worth. The value of each Point Item depends on their Y position (the position of the instance in Y-axis, vertical position). The maximum value of each Point Item is 199700.

Usually, this code was used for the Creation Event and End Step Event.
```
if y > 160
{
itemworth = round(((352-point_distance(x,y,x,160))/352)*199700)
}
else
{
itemworth = 199700
}
```
The variable, `itemworth` is used for the value of a Point Item.

`if y > 160` checks if the item is below the maximum value position, which is 160. If the item is below the maximum value position, the value of the variable `itemworth` will be changed to a value returned by `round(((352-point_distance(x,y,x,160))/352)*199700)`.

`round(((352-point_distance(x,y,x,160))/352)*199700)` may look very complicated, but it is a simple code. `point_distance` returns the distance between the position of the item and the maximum value position. `352` is the maximum distance. By subtracting from the maximum distance `352`, the integer range is now "reversed", in which the distance getting closer will result to a higher value. `/352` will turn the value to--.

This Point Item value code was used for Rejected Domination: Eternal Equinox (RD-1).

© Alexander James 2017 - ?
