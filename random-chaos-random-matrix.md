## How to make a random position on chaos
Did you know about the matrix and fractal?\
Basic example of sierpinski:
```c
void sierpinski_arrowhead_curve(unsigned order, double length)
{
    // If order is even we can just draw the curve.
    if ( 0 == (order & 1) ) {
        curve(order, length, +60);
    }
    else /* order is odd */ {
        turn( +60);
        curve(order, length, -60);
    }
}
void curve(unsigned order, double length, int angle)
{
    if ( 0 == order ) {
        draw_line(length);
    } else {
        curve(order - 1, length / 2, -angle);
        turn(angle);
        curve(order - 1, length / 2, angle);
        turn(angle);
        curve(order - 1, length / 2, -angle);
    }
}
```
in this example we draw a "sierpinski" fractal by simple equation.\
imagin the "dot's" without the lines. before that you drawing this shape(dot's) on a page and have coordination of all point.\
Each point have a (x, y) as position, and on that position you have a unique "prime number".\
Now you can choose two random position and times that two numbers for generating a unique RSA...\
for more information read [this](https://github.com/mosi-arch/documents/blob/main/prime-number-cryptography.md) and [this](https://github.com/mosi-arch/documents/blob/main/safe-unique-random-number.md)

### note
The fractal each times create from random point of the "plane", so each time unique random drawing.
