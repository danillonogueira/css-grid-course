# CSS Grid Course
Creating a grid:
~~~
display: grid;
~~~

Assigning columns and their respective width:
~~~
grid-template-columns: 100px auto 100px;
~~~

Assigning rows and their respective height:
~~~
grid-template-rows: 50px 50px;
~~~

Defining a gap that separates the grid cells:
~~~
grid-gap: 3px;
~~~

Fraction units can be used for assigning width:
~~~
grid-template-columns: 1fr 1fr 1fr;
~~~
~~~
grid-template-columns: 1fr 2fr 1fr;
~~~
~~~
grid-template-columns: repeat(3, 1fr);
~~~
