# CSS Grid Course
### Creating a grid:
~~~
display: grid;
~~~

### Assigning columns and their respective width:
~~~
grid-template-columns: 100px auto 100px;
~~~

### Assigning rows and their respective height:
~~~
grid-template-rows: 50px 50px;
~~~

### Defining a gap that separates the grid cells:
~~~
grid-gap: 3px;
~~~

### Fraction units can be used for defining width and height:
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
### Shorter method for defining width and height:
~~~
grid-template: repeat(2, 50px) / repeat(3, 1fr);
~~~
### Determines the space targeted element will take in a grid row:
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
### Determines the space targeted element will take in a grid column:
~~~
grid-row: 1 / 3;
~~~
~~~
grid-row: 1 / span 2;
~~~
~~~
grid-row: 1 / -1;
~~~
