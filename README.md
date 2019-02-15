# chart.js

- Declares `Chart` constructor.
- Does magical this bindings. This is a bad part of c3.js.
  - This makes the source code hard to read.
  - There is no benefit to do this.

# core.js

- Creates c3 object
- internal.beforeInit
  - The hook called before init method
- internal.afterInit
  - The hook called after init method
  - See [this](https://github.com/c3js/c3/blob/master/extensions/chart-bubble/bubble.js) for the example usages of beforeInit and afterInit
