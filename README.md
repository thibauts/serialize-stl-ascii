serialize-stl-ascii
===================
### STL ASCII serialization

Produces a [STL](http://en.wikipedia.org/wiki/STL_%28file_format%29) (STereoLithography) ASCII string from a mesh.

Install
-------

```bash
$ npm install serialize-stl-ascii
```

Example
-------

```javascript
var serializeSTL = require('serialize-stl-ascii');

var mesh = {
  positions: [
    [-1.0, 0.0, 0.0],
    [ 0.0, 1.0, 0.0],
    [ 1.0, 0.0, 0.0]
  ],
  cells: [
    [0, 1, 2]
  ]
}

var str = serializeSTL(mesh.cells, mesh.positions/*, faceNormals, solidName*/);
console.log(str);
/*
solid
  facet normal 0e+0 0e+0 -1e+0
    outer loop
      vertex -1e+0 0e+0 0e+0
      vertex 0e+0 1e+0 0e+0
      vertex 1e+0 0e+0 0e+0
    endloop
  endfacet
endsolid
*/
```