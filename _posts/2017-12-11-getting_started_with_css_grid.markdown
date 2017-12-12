---
layout: post
title:      "Getting Started With CSS Grid"
date:       2017-12-11 19:03:54 -0500
permalink:  getting_started_with_css_grid
---


CSS Grid is not a passing fad. It’s not impossible to get to work on multiple browsers. It is better than Bootstrap. It will take over in the next 2–3 years. After months of denial, I recently came to accept these truths and I encourage you to do the same.

(*This blog series is adopted from Rachel Andrews’ excellent video tutorials.)

In setting up a CSS Grid, the first thing that’s necessary is to set a class equal to “grid” on a container of div grids.

<a href="http://tinypic.com?ref=2aetap2" target="_blank"><img src="http://i64.tinypic.com/2aetap2.png" border="0" alt="Image and video hosting by TinyPic"></a>

Then in the CSS we next set this grid class equal to display: grid. This setup is visible below:

<a href="http://tinypic.com?ref=ddevdu" target="_blank"><img src="http://i67.tinypic.com/ddevdu.png" border="0" alt="Image and video hosting by TinyPic"></a>

Simple enough.

OK, but that doesn’t make any changes on the page. In order to do that, we need to specify grid-template-columns and/or grid-template-rows to the grid class. (Remember, columns are horizontal dividors while rows are vertical). 

As such, adding { display: grid; grid-template-columns: 200px, 200px, 200px } will create three columns, each with the length of 200px. However, columns will only be created as long as they correspond to the amount of divs that have been defined in the HTML. And divs that go over the amount of defined columns will wrap to the next line.

Conversely, adding grid-template-rows: 200px, 200px will create two rows, each 200px. So the divs must wrap two levels deep.

So, with four divs, and { display: grid; grid-template-columns: 200px, 200px, 200px; grid-template-rows: 200px, 200px }, what will our grid look like?

<a href="http://tinypic.com?ref=24b55pt" target="_blank"><img src="http://i68.tinypic.com/24b55pt.png" border="0" alt="Image and video hosting by TinyPic"></a>

Boom. Four divs. Three 200px columns. And two 200px rows. Who needs Bootstrap with columns and divs like that?
