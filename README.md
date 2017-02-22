# Pure CSS tree

[Demo](https://mrtcode.github.io/purecsstree/demo.html)

This is an experiment to make automatically aligning tree with automatically painted horizontal and vertical lines.

Why this approach is much better than calculating branch positions in JavaScript?

* No JavaScript or hard coded positions. Add more branches and the tree automatically aligns itself.
* Advanced CSS animations can be used (i.e. when mouse hovers a branch, the tree can nicely spread)
* No forced browser reflows when positioning branches - browser can optimize it self because all positioning is done automatically in flexbox

This tree doesn't use any javascript to position branches, that means no need to track when branch text (and dimensions) changes and do expensive position recalculations.

## Painting lines

Horizontal lines are very simple, it's just `border-bottom: 1px solid #f0f0f0`

The most hardest problem to solve in this demo is vertical lines. This isn't fully solved and in some cases lines are missing.

There are more ways to draw vertical lines, but in every case there are some side effects.

### Drawing vertical lines in a canvas HTML5 element

Good until a tree gets bigger. When canvas element dimensions get too big the fps rate drops down significantly. Also there are very different performance result between different browsers and devices making this method unreliable.
Canvas element was made only a little bigger than browser viewport and when a big tree is scrolled the canvas element is also automatically recentered and lines repainted. This allows more or less infinite tree size, but canvas dimensions are still to big (especially if browser window is maximized and high resolution screen is used) and doesn't solve performance problems.

### Drawing vertical lines in SVG

When a tree gets a little bit bigger SVG slows down significantly.




















