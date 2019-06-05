# CSS Grid Course
### Creating a grid
~~~
display: grid;
~~~
### Assigning columns and their respective width
~~~
grid-template-columns: 100px auto 100px;
~~~
### Assigning rows and their respective height
~~~
grid-template-rows: 50px 50px;
~~~
### Defining a gap that separates the grid cells
~~~
grid-gap: 3px;
~~~
### Fraction units can be used for defining width and height
~~~
grid-template-columns: 1fr 1fr 1fr;
~~~
~~~
grid-template-columns: 1fr 2fr 1fr;
~~~
~~~
grid-template-columns: repeat(3, 1fr);
~~~
~~~
grid-template-rows: repeat(2, 50px);
~~~
### Shorter method for defining width and height
~~~
grid-template: repeat(2, 50px) / repeat(3, 1fr);
~~~
### Determines the space targeted element will take in a grid row
~~~
grid-column-start: 1;
grid-column-end: 3;
~~~
Or
~~~
grid-column: 1 / 3;
~~~
~~~
grid-column: 1 / span 2;
~~~
~~~
grid-column: 1 / -1;
~~~
### Determines the space targeted element will take in a grid column
~~~
grid-row: 1 / 3;
~~~
~~~
grid-row: 1 / span 2;
~~~
~~~
grid-row: 1 / -1;
~~~
### Using grid-area for determining space
~~~
.container {
  grid-template-areas:
    "m h h"
    "m c c"
    "m f f";
}

.header {
  grid-area: h;
}

.menu {
  grid-area: m;
}

.content {
  grid-area: c;
}

.footer {
  grid-area: f;
}
~~~
### Setting a dynamic number of columns
~~~
.container {
  grid-template-columns: repeat(auto-fit, 100px);
}
~~~
### Setting a dynamic width for the columns
~~~
.container {
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
}
~~~
*The __minmax__ property sets a minimum and maximum width columns can occupy in the grid. It seems to be a good practice so as to avoid unwanted blank spaces in the grid. The max value set in fraction units plays an important role here.*
### Setting a dynamic number of rows
~~~
grid-auto-rows: 100px;
~~~
### Creating a dynamic grid for cells with varying sizes
~~~
.container {
  grid-auto-flow: dense;
}

.horizontally-wide-cell {
  grid-column: span 2;
}

.vertically-wide-cell {
  grid-row: span 2;
}

.bigger-cell {
  grid-column: span 2;
  grid-row: span 2;
}
~~~
*The __grid-auto-flow__ property accepts other values. The __dense__ value was used as an example because it seems to be the one that best does the trick. You can check alternative values [here](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow).*
