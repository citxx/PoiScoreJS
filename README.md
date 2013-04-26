PoiScoreJS
==========

This library allows you to generate different variations of [PoiScore](http://www.yutapoi.com/poiclasses/event/moscow-2013-spring/#h.19974gy77hpx) PDFs on client side.


Dependencies
============

PoiScoreJs depends only on [jsPDF](https://github.com/MrRio/jsPDF).


Usage
=====

In order to use PoiScoreJS you should first include the library and all its dependencies in the html head:

```html
<script type="text/javascript" src="assets/jspdf.min.js"></script>
<script type="text/javascript" src="assets/poiscore.js"></script>
```

And then you can use it as follows:

```javascript
var score = new jsPDF();
var renderer = new PoiScore.jsPDFRenderer(score);
PoiScore.gen(renderer, [  // Generate PDF
    {},  // Default page
    {linesInDescriptionBox: 0, commentBoxFraction: 0},  // Page without description and comment boxes
    {pageNumeration: false, groupNumeration: false},  // Page without group and page numbers
    {    // A page with:
        cellsPerSubgroup: 3,        // * subgroup size of 3 cells
        subgroupsPerGroup: 4,       // * group size of 4 subgroups 
        groupsPerLine: 3,           // * line size of 3 groups
        commentBoxFraction: 0.35    // * width of comment box as a fraction of 1
    })
]);

score.save("PoiScore.pdf");  // Force browser to "download" resulting document
```


License
=======

(MIT License)

Copyright (c) 2013 Artem Tabolin, https://github.com/citxx/PoiScoreJS

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
