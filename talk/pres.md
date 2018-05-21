# Intro to flexbox

# What is flexbox for?
* It is a layout tool
	* Along a single axis
		* horizontally, or
		* vertically

# Basic terminology
* flex container
* flex item
* main axis
* cross axis

# Basic operation (your first cheat sheet!)
Apply this to the flex container
* turn flexbox on
	```
	display: flex;
	```
* set the direction
	```
	flex-direction: [row, column, row-reverse, column-reverse];
	```
* set the main axis alignment
	```
	justify-content: [flex-start, flex-end, center, stretch, space-around, space-between];
	```
* set the cross axis alignment
	```
	align-items: [flex-start, flex-end, center, stretch, space-around, space-between];
	```

# Wrapping
To the flex container:
* wrapping
	```
	flex-wrap: [wrap, wrap-reverse];
	```
* while wrapping, control spacing between rows 
	```
	align-content: [fl..-s...., fl..-e.., ce...., st....., sp...-ar...., sp...-b......]; 
	```
* alignment (justify-content and align-items)
	* applies to the rows individually

# Vary individual items
* over-ride cross axis alignment
	```
	align-self: [flex-start, flex-end, center, stretch, space-around, space-between];
	```
* re-ordering
	```
	order: [integer];
	```

# 3 keys to layout success
All these operate on the main axis
* flex-grow
	* how does a flex item grow?
* flex-shrink
	* how does a flex item shrink?
* flex-basis
	* sets the ideal width (or height)

# flex-grow
Applies to each row in the flex container
To calculate:
* calculate unused space in the flex container
* add up all the flex-grow values
* divide each flex item's flex-grow by the total to get a ratio for growth
* allocate free space to each flex item according to the ratio

```
free space * (flex-grow / total of flex-grows)
```
## Example 1
* flex container 400px
* 3 items 
	* 100px each
	* each with ```flex-grow: 1;```
* free space = 100px
* total of flex-grow values = 3
* each item gains 100px * 1/3 = 33.3px

## Example 2
* flex container 400px
* 3 items 
	* 100px each
	* DIVs 1 & 2 with ```flex-grow: 1;```
	* DIV 3 with ```flex-grow: 2;```
* free space = 100px
* total of flex-grow values = 4
* DIVs 1 & 2 gains 100px * 1/4 = 25px
* DIV 3 gains 100px * 2/4 = 50px

## DEMO TIME!
* flex-grow.html

# flex-shrink
Similar to flex-grow...

But this time the flex-shrink creates a ratio at which the flex items must shrink to fit width.

# flex-basis
* determines the _ideal width_ of a flex-item
* how is width determined?
	* flex-basis wins
	* width property on a flex item
	* content width
* default
	* auto
	* defers to the rules above
* flex-basis property constrained by min-width and max-width

# Getting started in production
* browser support (caniuse.com)
* start small
	* center a single element on both axes
	* add an optional element beside another 
		* no matter whether 1 or both elements are displayed, you need to center them
	* you could use it to layout a menu
		* perhaps the menu needs to display horizontally for wide displays and vertically on mobile

# Resources