# jquery.transformable.js
Transform, rotate, skew and scale divs in same manner as draggable/resizable in jquery-ui

##Simple Usage:
```
$('#mydiv').draggable().transformable().resizable();
```
##Basic options and callbacks:
```
$('#mydiv').transformable( {
        rotateStart: function(e,ui){},
        rotate:      function(e,ui){},
        rotateStop:  function(e,ui){},
        skewStart:   function(e,ui){},
        skew:        function(e,ui){},
        skewStop:    function(e,ui){},
        skewXStart:   function(e,ui){},
        skewX:        function(e,ui){},
        skewXStop:    function(e,ui){},
        skewYStart:   function(e,ui){},
        skewY:        function(e,ui){},
        skewYStop:    function(e,ui){},
        scaleStart:  function(e,ui){},
        scale:       function(e,ui){},
        scaleStop:   function(e,ui){},
        rotatable:   [true|false],
        skewable:    [true|false],
        scalable:    [true|false],
        containment: [true|false] //still somewhat experimental
});

//get extended offset information
var o=$('#mydiv').tOffset();
/* o will be:
{
        left:   number,  //the furthest left point of element on page (bounding box) 
        right:  number,  // ditto for right
        top:    number,
        bottom: number,
                // position of corners with topleft being the 
                // untransformed topleft corner
        corners:[  {x: topleftx,     y: toplefty}, 
                   {x: toprightx,    y: toprighty},
                   {x: bottomrightx, y: bottomrighty},
                   {x: bottomleftx,  y: bottomlefty}
                ],
        center: {x: centerx, y: centery},
                //affine transform matrix of this element
        matrix: [number,number,number,number,number,number],
                //sum off this and parents' matricies
        totalmatrix: [number,number,number,number,number,number],
                //whether this or any parents have transformations
        transformed: bool
}

*/

//destroy
$('#mydiv').transformable('destroy');
```
## Dependencies:
* jquery
* jquery-ui
* jquery.transform2d.js courtesy of https://github.com/louisremi/jquery.transform.js/
