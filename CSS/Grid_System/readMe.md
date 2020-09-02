


<h2 style="color:#66fcf1" align="center">GRID LAYOUT</h2>

<hr style="height:4px">

<p style="font-family:Comic Sans MS">CSS Grid Layout is the most powerful layout system available in CSS. It is a 2-dimensional system, meaning it can handle both columns and rows, unlikeflexbox which is largely a 1-dimensional system. We work with Grid Layout by applying CSS rules both to a parent element (which becomes the Grid Container) and to that element’s children (which become Grid Items).    
</p>

<h4 style="color:">Parent (Grid Container)</h4>
<pre>
display: grid | inline-grid;
</pre>

<hr>
<strong>grid-template-columns & grid-template-rows</strong> :

<pre>[optional: line-name, in square brackets] track-size | repeat ; 
Where,
line-name:an arbitrary name for this item. If no name assigned, a number is used
track-size: length, %, fr, auto</pre>

Examples:

<pre>.myClass {
		    grid-template-columns: [col1] 40px [col2] 3fr;
		    grid-template-rows: 50% 25vh auto;
		    }
	  .anotherClass {
		            grid-template-rows: repeat(2, 350px [name]) 10%;
	     	        }
		\\translates to\\
	  .anotherClass {
		            grid-template-rows: 350px [name] 350px [name] 10%;
		            }</pre>

<strong>grid-template-columns & grid-template-rows</strong> :

<pre>[optional: line-name, in square brackets] track-size | repeat ; 
Where,
line-name:an arbitrary name for this item. If no name assigned, a number is used
track-size: length, %, fr, auto</pre>

Examples:

<pre>.myClass {
		    grid-template-columns: [col1] 40px [col2] 3fr;
		    grid-template-rows: 50% 25vh auto;
		    }
	  .anotherClass {
		            grid-template-rows: repeat(2, 350px [name]) 10%;
	     	        }
		\\translates to\\
	  .anotherClass {
		            grid-template-rows: 350px [name] 350px [name] 10%;
		            }</pre>

<strong>grid-template-areas:</strong> 

List of names of areas. First, name areas via selector. Then specify layout via this property. Area name must be specified for each column/row. A . indicates no content in this row/column.

		Note: in this example, the lines are named automatically: header-start, header-end, article-start, article-end, etc.

Example:


		.class1 {
	         	 grid-area: header;
		         }
		     ---------------
		     .class2 {
		        grid-area: article;
		        }
		     -----------------
		     .class3 {
		        grid-area: aside;
		        }
	         -----------------
		.wrapper {
		         grid-template-columns: 1fr 3fr;
		         grid-template-rows: auto;
		         grid-template-areas: 
		        "header header header header"
		        "aside . article article";
		        }
<strong>grid-template:</strong> 

Shorthand for grid-template-rows, grid-template-columns, and grid-template-areas in 1 declaration. Not covered in class.  

Example:


```
grid-template: 
            "a a a" 40px
            "b c c" 40px
            "b c c" 40px / 1fr 1fr 1fr;

grid-template: 
            "b b a" auto
            "b b c" 2ch
            "b b c" 1em / 20% 20px 1fr;
            
grid-template: 
            "a a ." minmax(50px, auto)
            "a a ." 80px
            "b b c" auto / 2em 3em auto;
```
<strong>grid-column-gap & grid-row-gap</strong>   

grid-column-gap: <number>;
grid-row-gap: <number>;
		Distance between rows and/or columns. At one point, only pixels were accepted for this - browser bug?

<strong>grid-gap:</strong>

Shorthand for grid-column-gap and grid-row-gap. 
1 number = same in all directions
2 numbers = row column

<strong>justify-items:</strong>   

```
justify-items: start | end | center | stretch;
               align grid items on row axis
               Stretch is default
```

<strong>align-items:</strong>   

```
align-items:  start | end | center | stretch;
		      align grid items on column axis
		      Stretch is default
```

<strong>justify-content</strong>

```
justify-content: start | end | center | stretch | space-around | space-between | space-evenly;
```


If size of grid container is bigger than total of grid items, you can align grid items within the container (like flexbox). This works on row axis.

<strong>align-content</strong>

```
align-content:  start | end | center | stretch | space-around | space-between | space-evenly;
```

If size of grid container is bigger than total of grid items, you can align grid items within the container (like flexbox). This works on column axis.

<strong>grid-auto-columns
grid-auto-rows</strong>

```
grid-auto-columns
grid-auto-rows: <track-size>;
```

If you create grid cells beyond those specified in grid-template-columns and grid-template-rows, this specifies how big these extra rows/columns should be.

> grid: shorthand for all of the above properties. Not covered in class.





#### Children (Grid Items)

<hr>

​	<strong>grid-column-start,grid-column-end & grid-row-start</strong>

```
grid-column-start
grid-column-end
grid-row-start
grid-row-end: <number> | <name> | span <number> | span <name> | auto;
```

​		This is the longhand for declaring individual values for start and end points for rows and columns.

Example:

​	

```
.class1 {
		grid-column-start: 1;
		grid-column-end: span 4;
		grid-row-start: 3;
		grid-row-end: span footer-end;
	}
```

<strong>grid-column & grid-row</strong>

```
grid-column
grid-row: <start-line> / <end-line> | <start-line> / span <value>;
```


​	Combines start and end values, as used extensively in class.

​	Example: 
​	

```
.class1 {
		grid-column: 1 / span 4;
		grid-row: 3 / span footer-end;
	}
```

<strong>grid-area</strong>	

```
grid-area:  <name> | <row-start> / <column-start> / <row-end> / <column-end>;
OR
<name>;
```

​	<u>If you're confused, no wonder. grid-area can be used in 2 different ways:</u>
​		a. Assign a name for the grid-template-areas property (see above example under grid container/grid-template-areas)

​		b. Assign a name AND the dimensions for a grid-template-areas property. If you use this methodology, you would not necessarily need a grid-template-rows and grid-template-columns declaration, depending on other factors.

Example:
		

```
.class1 {
		  grid-area: 1 / name3 / namedline / 4;
		}

justify-self: start | end | center | stretc

<h2 style="color:#66fcf1" align="center">GRID LAYOUT</h2>

<hr style="height:4px">

<p style="font-family:Comic Sans MS">CSS Grid Layout is the most powerful layout system available in CSS. It is a 2-dimensional system, meaning it can handle both columns and rows, unlikeflexbox which is largely a 1-dimensional system. We work with Grid Layout by applying CSS rules both to a parent element (which becomes the Grid Container) and to that element’s children (which become Grid Items).    
</p>

<h4 style="color:">Parent (Grid Container)</h4>
<pre>
display: grid | inline-grid;
</pre>

<hr>
<strong>grid-template-columns & grid-template-rows</strong> :

<pre>[optional: line-name, in square brackets] track-size | repeat ; 
Where,
line-name:an arbitrary name for this item. If no name assigned, a number is used
track-size: length, %, fr, auto</pre>

Examples:

<pre>.myClass {
		    grid-template-columns: [col1] 40px [col2] 3fr;
		    grid-template-rows: 50% 25vh auto;
		    }
	  .anotherClass {
		            grid-template-rows: repeat(2, 350px [name]) 10%;
	     	        }
		\\translates to\\
	  .anotherClass {
		            grid-template-rows: 350px [name] 350px [name] 10%;
		            }</pre>

<strong>grid-template-columns & grid-template-rows</strong> :

<pre>[optional: line-name, in square brackets] track-size | repeat ; 
Where,
line-name:an arbitrary name for this item. If no name assigned, a number is used
track-size: length, %, fr, auto</pre>

Examples:

<pre>.myClass {
		    grid-template-columns: [col1] 40px [col2] 3fr;
		    grid-template-rows: 50% 25vh auto;
		    }
	  .anotherClass {
		            grid-template-rows: repeat(2, 350px [name]) 10%;
	     	        }
		\\translates to\\
	  .anotherClass {
		            grid-template-rows: 350px [name] 350px [name] 10%;
		            }</pre>

<strong>grid-template-areas:</strong> 

List of names of areas. First, name areas via selector. Then specify layout via this property. Area name must be specified for each column/row. A . indicates no content in this row/column.

		Note: in this example, the lines are named automatically: header-start, header-end, article-start, article-end, etc.

Example:


		.class1 {
	         	 grid-area: header;
		         }
		     ---------------
		     .class2 {
		        grid-area: article;
		        }
		     -----------------
		     .class3 {
		        grid-area: aside;
		        }
	         -----------------
		.wrapper {
		         grid-template-columns: 1fr 3fr;
		         grid-template-rows: auto;
		         grid-template-areas: 
		        "header header header header"
		        "aside . article article";
		        }
<strong>grid-template:</strong> 

Shorthand for grid-template-rows, grid-template-columns, and grid-template-areas in 1 declaration. Not covered in class.  

Example:


```
grid-template: 
            "a a a" 40px
            "b c c" 40px
            "b c c" 40px / 1fr 1fr 1fr;

grid-template: 
            "b b a" auto
            "b b c" 2ch
            "b b c" 1em / 20% 20px 1fr;
            
grid-template: 
            "a a ." minmax(50px, auto)
            "a a ." 80px
            "b b c" auto / 2em 3em auto;
```
<strong>grid-column-gap & grid-row-gap</strong>   

grid-column-gap: <number>;
grid-row-gap: <number>;
		Distance between rows and/or columns. At one point, only pixels were accepted for this - browser bug?

<strong>grid-gap:</strong>

Shorthand for grid-column-gap and grid-row-gap. 
1 number = same in all directions
2 numbers = row column

<strong>justify-items:</strong>   

```
justify-items: start | end | center | stretch;
               align grid items on row axis
               Stretch is default
```

<strong>align-items:</strong>   

```
align-items:  start | end | center | stretch;
		      align grid items on column axis
		      Stretch is default
```

<strong>justify-content</strong>

```
justify-content: start | end | center | stretch | space-around | space-between | space-evenly;
```


If size of grid container is bigger than total of grid items, you can align grid items within the container (like flexbox). This works on row axis.

<strong>align-content</strong>

```
align-content:  start | end | center | stretch | space-around | space-between | space-evenly;
```

If size of grid container is bigger than total of grid items, you can align grid items within the container (like flexbox). This works on column axis.

<strong>grid-auto-columns
grid-auto-rows</strong>

```
grid-auto-columns
grid-auto-rows: <track-size>;
```

If you create grid cells beyond those specified in grid-template-columns and grid-template-rows, this specifies how big these extra rows/columns should be.

> grid: shorthand for all of the above properties. Not covered in class.





#### Children (Grid Items)

<hr>

​	<strong>grid-column-start,grid-column-end & grid-row-start</strong>

```
grid-column-start
grid-column-end
grid-row-start
grid-row-end: <number> | <name> | span <number> | span <name> | auto;
```

​		This is the longhand for declaring individual values for start and end points for rows and columns.

Example:

​	

```
.class1 {
		grid-column-start: 1;
		grid-column-end: span 4;
		grid-row-start: 3;
		grid-row-end: span footer-end;
	}
```

<strong>grid-column & grid-row</strong>

```
grid-column
grid-row: <start-line> / <end-line> | <start-line> / span <value>;
```


​	Combines start and end values, as used extensively in class.

​	Example: 
​	

```
.class1 {
		grid-column: 1 / span 4;
		grid-row: 3 / span footer-end;
	}
```

<strong>grid-area</strong>	

```
grid-area:  <name> | <row-start> / <column-start> / <row-end> / <column-end>;
OR
<name>;
```

​	<u>If you're confused, no wonder. grid-area can be used in 2 different ways:</u>
​		a. Assign a name for the grid-template-areas property (see above example under grid container/grid-template-areas)

​		b. Assign a name AND the dimensions for a grid-template-areas property. If you use this methodology, you would not necessarily need a grid-template-rows and grid-template-columns declaration, depending on other factors.

Example:
		

```
.class1 {
		  grid-area: 1 / name3 / namedline / 4;
		}

justify-self: start | end | center | stretch;
	Aligns content in a grid item on the row axis. Overrides justify-items. 

align-self: start | end | center | stretch;
	Aligns content in a grid item on the column axis. Overrides align-items.
```

<hr><h5>auto-fit & auto-fill</h5>

<hr>

`auto-fill` FILLS the row with as many columns as it can fit. So it creates implicit columns whenever a new column can fit, because it’s trying to FILL the row with as many columns as it can. The newly added columns can and may be empty, but they will still occupy a designated space in the row.

`auto-fit` FITS the CURRENTLY AVAILABLE columns into the space by expanding them so that they take up any available space. The browser does that after FILLING that extra space with extra columns (as with `auto-fill` ) and then collapsing the empty ones.

h;
	Aligns content in a grid item on the row axis. Overrides justify-items. 

align-self: start | end | center | stretch;
	Aligns content in a grid item on the column axis. Overrides align-items.
```

<hr><h5>auto-fit & auto-fill</h5>

<hr>

`auto-fill` FILLS the row with as many columns as it can fit. So it creates implicit columns whenever a new column can fit, because it’s trying to FILL the row with as many columns as it can. The newly added columns can and may be empty, but they will still occupy a designated space in the row.

`auto-fit` FITS the CURRENTLY AVAILABLE columns into the space by expanding them so that they take up any available space. The browser does that after FILLING that extra space with extra columns (as with `auto-fill` ) and then collapsing the empty ones.

