Hi There!

You can use this includes folder to start your own projects more quickly and easily.

*SASS*

The SASS system has been completely overhauled in structure to provide a more modular and reusable experience.  Everything starts in ./sass/style.scss.  Linked to from this stylesheet are global variables ('./sass/library/_global_vars.scss') and mixins (./sass/library/_mixins.scss).  From there, CSS is included by creating new *segments*.  Simply copy the example segment (./sass/segments/example) and rename the folder (ex. header or sidebar or checkout).  This will represent a cohesive section or segment of your site.  Your CSS will eventually consist of the sum of your distinct segments.  After renaming your new segment, include the _index in your main style.scss and start defining styles in ./sass/segments/{segment name}/_base.scss.  If your segment is repsponsive, uncomment the responsive includes in your _index.scss and use the responsive sheets located in ./sass/segments/{segment name}/res.

Some documentation about mixins:

@include box-sizing($area)

//  $area - can accept either border, padding, or content;
\\  This mixin will apply the specified box sizing to the element,
\\  along with the needed vendor prefixes to support all browsers;

@include align($direction)

//  $direction - can accept either left, right, or center;
\\  This mixin will apply the specified text alignment to the element
\\  along with all of its children, both direct and indirect;

@include transition($time, $type)

//  $time - can accept a valid css time value;
//	$type - can accept a valid css transition type | Defaults to 'all';
\\  This mixin will apply a cross browser transition of the type and
\\  time specified to an element;

@extend %margin-auto

\\  Applies margin-left: auto; and margin-right: auto; to an element;

@extend %rotate

\\  Rotates stuff
\\  $deg is number of degrees to rotate.
\\  $xtrans is distance to move x axis
\\  $ytrans is distance to move y axis