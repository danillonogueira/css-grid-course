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
### Using grid-template-areas for determining space
~~~
.container {
  grid-template-areas:
    "m h h h h h h h h h h h"
    "m c c c c c c c c c c c"
    "m f f f f f f f f f f f";
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
![template areas](/assets/TemplateAreas.JPG)
### Using named lines for determining space
~~~
.container {
  grid-template-columns: [main-start] 1fr [content-start] 5fr [content-end main-end];
  grid-template-rows: [main-start] 40px [content-start] auto [content-end] 40px [main-end]; 
}

.header {
  grid-column: main;
}

.content {
  grid-area: content;
}

.footer {
  grid-column: main;
}
~~~
![named lines](/assets/NamedLines.JPG)<br />
*Interestingly, the dash synthax allows us to write less when targeting the grid cells. This means we just have to use the sufixes __-start__ and __-end__ when targeting the grid container.*
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
Without grid-auto-flow | With grid-auto-flow
------------------- | ----------------------
![without auto-flow](assets/WithoutAutoFlow.JPG) | ![with auto-flow](assets/WithAutoFlow.JPG)
*The __grid-auto-flow__ property accepts other values. The __dense__ value was used as an example because it seems to be the one that best does the trick, forcing smaller cells to go up the grid if necessary. You can check alternative values [here](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow).*
### Using justify and align properties in grid
~~~
justify-content: center;
~~~
~~~
justify-content: space-around;
~~~
~~~
justify-content: space-evenly;
~~~
~~~
align-content: center;
~~~
~~~
align-content: end;
~~~
More options [here](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content).
### Auto-fit vs auto-fill
~~~
.auto-fit-container {
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    grid-template-rows: 100px 100px;
}

.auto-fill-container {
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    grid-template-rows: 100px 100px;
}
~~~
![auto-fit vs auto-fill](/assets/autofitvsautofill.jpg)
