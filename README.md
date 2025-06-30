Ryan's c64 notes/demos

bouncing ball / breakout
https://tomasp.net/commodore64/


10 PRINT "HELLO WORLD"
(type run, press enter)


10 FOR Y = 1 TO 10

You can either retype the line to replace it
change 10 to 100 (enter)

You can also copy and paste lines this way

10 PRINT "HELLO"
move cursor to 10,  replace with 20,   press enter and it will duplicate
there is may be some trickiness doing this with emulator, because it can erase to the right (like insert key function)



## Changing environment colors

POKE 53281,0  : REM Sets background color to black

POKE 646, C   : Change Default Text Color

Where C is a number between 0–15 representing the color:

```
Color #	Color Name
0	Black
1	White
2	Red
3	Cyan
4	Purple
5	Green
6	Blue
7	Yellow
8	Orange
9	Brown
10	Light Red
11	Dark Gray
12	Medium Gray
13	Light Green
14	Light Blue
15	Light Gray
```


## "Etch a sketch" drawing
10 POKE 788,82


## wavy line scroll

10 FOR Y = 1 TO 20
20 X = 10 + INT(5*SIN(Y/2))
30 PRINT TAB(X);"*"
40 NEXT Y



## another wavy scroll?

5 POKE 646,2   : REM red text
10 FOR Y = 1 TO 20
20 A = Y/2 + T/5
30 X = 10 + INT(5*SIN(A))
40 PRINT TAB(X);"*"
50 NEXT Y
60 T = T + 1 : GOTO 10


## shake the screen

10 poke 53248+22,int(192+4+3*sin((time*3.456+rnd(1)*.5))): goto 10