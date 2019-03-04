## `//src/chart.js`

This file only includes the Chart constructor.

- Declares `Chart` constructor.
- Does magical this bindings. This is a bad part of c3.js.
  - This makes the source code hard to read.
  - There is no benefit to do this.

## `//src/core.js`

This file includes central mechanism of drawing of charts.

- Creates c3 object
- internal.beforeInit
  - The hook called before init method
- internal.afterInit
  - The hook called after init method
  - See [this](https://github.com/c3js/c3/blob/master/extensions/chart-bubble/bubble.js) for the example usages of beforeInit and afterInit

- internal.initChartElements
  - This function calls 5 methods initBar, initLine, initArc, initGauge, and initText
  - I think the if statement for each method is very strange because they never become false.

## `//src/size.js`

This files includes the methods about calculation of chart sizes.

- `internal.getParentRectValue(key: string)`
  - look up the key from the parent's bounding DOMRect.
  - If the value of the given key doesn't exist on the parent, it look for the parent's parents, recursively.
  - This function includes special support of some old IE. This is probably now unnecessary.

# issues

## https://github.com/c3js/c3/issues/2567

- Now this is top priority (Feb 2019)
- Need to reproduce the issue on the local env first
- -> This doesn't happen in htdocs/samples/resize.html

# DOM APIs

## Element.getBoundingClientRect

- https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect
