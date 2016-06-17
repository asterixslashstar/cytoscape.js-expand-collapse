cytoscape-expand-collapse
================================================================================


## Description

This extension provides an interface to expand/collapse nodes.

## API

* Note that compounds are nodes.

`cy.expandCollapse(options)`
To initialize/set options whenever you want.

* Following functions get options parameter to apply during a particular event unlike the function above.

`eles.collapse(options)`
Collapse node(s).

`eles.collapseRecursively(options)`
Collapse node(s) and their child nodes.

`cy.collapseAll(options)`
Collapse all nodes on graph (recursively).

`eles.expand(options)`
Expand node(s).

`eles.expandRecursively(options)`
Expand node(s) and their child compounds.

`cy.expandAll(options)`
Expand all nodes on graph (recursively).

`ele.isExpandable()`
Get whether node is expandable (or is collapsed)

`ele.isCollapsible()`
Get whether node is expandable (or is collapsed).

`eles.expandableNodes()`
Returns expandable nodes from given set of elements.

`eles.collapsibleNodes()`
Returns collapsible nodes from given set of elements.

`cy.expandableNodes()`
Returns expandable nodes from whole graph.

`cy.collapsibleNodes()`
Returns collapsible nodes from whole graph.


## Default Options
```javascript
    var options = {
      layoutBy: null, // for rearrange after expand/collapse. It's just layout options or whole layout function. Choose your side!
      fisheye: true, // to push nodes around currently expanding node away
      animate: true, // animate nodes & zoom
      ready: function () { }, // callback when expand/collapse initialized
      undoable: true // and if undoRedoExtension exists
    };
```


## Dependencies

 * Cytoscape.js ^1.7.0
 * cytoscape-undo-redo.js(optional) ^1.0.1
 * cytoscape-cose-bilkent.js(optional/suggested for layout after expand/collapse) ^1.3.6


## Usage instructions

Download the library:
 * via npm: `npm install cytoscape-expand-collapse`,
 * via bower: `bower install cytoscape-expand-collapse`, or
 * via direct download in the repository (probably from a tag).

`require()` the library as appropriate for your project:

CommonJS:
```js
var cytoscape = require('cytoscape');
var expand-collapse = require('cytoscape-expand-collapse');

expand-collapse( cytoscape ); // register extension
```

AMD:
```js
require(['cytoscape', 'cytoscape-expand-collapse'], function( cytoscape, expand-collapse ){
  expand-collapse( cytoscape ); // register extension
});
```

Plain HTML/JS has the extension registered for you automatically, because no `require()` is needed.


## Publishing instructions

This project is set up to automatically be published to npm and bower.  To publish:

1. Set the version number environment variable: `export VERSION=1.2.3`
1. Publish: `gulp publish`
1. If publishing to bower for the first time, you'll need to run `bower register cytoscape-expand-collapse https://github.com/iVis-at-Bilkent/cytoscape.js-expand-collapse.git`
