## Introduction
CSS is always a confused part of front end development. In this blog, I will share you how to style a basic html page.

## Table of Contents
  - Use grid to layout elements
  - Use grid start and end to sytle header and footer
  - Use grid-column to expand certain elements
  - Layout done, add some color
## Content
This is how original plain html looks like:

![plain_html.png](https://c1.staticflickr.com/5/4766/26638765248_8d8086d7c7_b.jpg)


### 1. Use grid to layout elements
As you can see, in html we have a div with a class name grid. This div will become our container for all other html elements. In this container, we will use grid to arrange elements.

```css
.grid {
  display: grid;
  grid-template-rows: 5% 30% 10% 30% 20% 5%;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
}
```

the above code can be reformed into following code

```css
.grid {
  display: grid;
  grid-template: 5% 30% 10% 30% 20% 5% / repeat(6, 1fr);
}
```

The plain html looks like this:

![grid_templated.png](https://c1.staticflickr.com/5/4672/26638765368_aeb6ca1b2f_b.jpg)

### 2. Use grid start and end to style header and footer
After grid arrangement, each element takes one column. However, some elements have to expand along the whole page such as header and footer. so we can do that with grid-column-start and grid-column-end.

```css
header, .banner, .about, footer {
  grid-column-start: 1;
  grid-column-end: 7;
}
```

Then the html look like this:

![after_gridExpand.png](https://c1.staticflickr.com/5/4695/40467308622_7d1fcd3157_b.jpg)

### 3. Use grid-column to expand certain elements
Unlike header or footer, some elements they dont need to expand along the whole page but several columns, such as address and hours. In this case, we should use grid-column like this:

```css
.address {
  grid-column: 1 / span 2;
}

.hours {
  grid-column: 3 / span 2;
}
/* ...more similar code... */
```

Then the html look like this:

![after_span.png](https://c1.staticflickr.com/5/4750/39614631235_aecb53cda9_b.jpg)


### 4. Layout done, add some color
After above steps, the layout is done. Now let us add some color to the background and change the font color:

```css
body {
  background-color: #ffffff;
  color: #db6363;
  text-align: center;
}

header {
  background-color: #ffffff;
  color: #dc6363;
  padding-top:10px;
}

.banner {
  background-color: #db6363;
  padding-top: 10px;
  font-family: Poppins;
  font-size: 84px;
  letter-spacing: 3.7px;
  color: #ffffff;
}

/* more code can be viewed in git repository */
```

The final view look like this:

![final_view.png](https://c1.staticflickr.com/5/4616/39614631055_9717662f08_b.jpg)

## Conclusion
Css is very important in front end development, it is better to practice more to keep your profiency of it.

## Code Reference

https://github.com/BridgeNB/CSS-Practice-PupSpa.git

## Thanks
Speical thanks to codecademy for providing study material!
