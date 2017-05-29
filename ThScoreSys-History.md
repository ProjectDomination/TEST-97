# ID 892793336 - THScoreSys (thscoresys.gmk)

## Version 1.0.0
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
The variable, `itemworth` is used for the value of a Point Item; the score you get when collecting a Point Item.

`if y > 160` checks if the item is below the maximum value position, which is `160`. If the item is below the maximum value position, the value of the variable `itemworth` will be changed to a value returned by `round(((352-point_distance(x,y,x,160))/352)*199700)`. Otherwise, the value of the variable `itemworth` will be changed to the maximum value, `199700`.

`round(((352-point_distance(x,y,x,160))/352)*199700)` may look very complicated, but it is a simple code. `point_distance(x1,y1,x2,y2)` returns the distance between the position of the item and the maximum value position. `352` is the maximum distance. By subtracting from the maximum distance `352`, the value range is now "reversed", in which the distance getting closer will result to a higher value. `/352` will turn the value into a value between 0 and 1, which is necessary for creating our own value range. `*199700` is used to create the value range, in which the maximum value is `199700`, and will also provide the exact value based on the Y position of the item. Finally, `round(x)` is executed to return the rounded up value.

This Point Item value code was used for Rejected Domination: Eternal Equinox (RD-1).
