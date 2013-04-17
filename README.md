PoiScoreJS
==========

This library allows you to generate different variations of [PoiScore](http://www.yutapoi.com/poiclasses/event/moscow-2013-spring/#h.19974gy77hpx) PDFs on client side.

Usage
=====

```javascript
var score = PoiScore.gen([  // Generate PDF
    PoiScore.properties({}),  // Default page
    PoiScore.properties({withDescription: false}),  // Page without description area
    PoiScore.properties({withSideField: false}),  // Page without fields
    PoiScore.properties({    // A page with:
        subGroupSize: 3,     // * subgroup size of 3 cells
        groupSize: 4,        // * group size of 4 subgroups 
        lineSize: 3,         // * line size of 3 groups
        sideFieldSize: 35    // * specific side field size (in mm)
    })
]);

score.save("PoiScore.pdf");  // Force browser to "download" resulting document
```
