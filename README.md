responsive-font-size
====================

A SASS mixin to ease creating layouts which scale the font-size based on screen width. Relies on media queries.

Supplied with four parameters, this mixin will intelligently figure out how define the font sizes for you.

Usage:

    @import "responsive-font-size";

    p {
        @include responsive-font-size (
            $min-font-size: 1.8em,
            $max-font-size: 3.7em,
            $min-screen-width: 640px,
            $max-screen-width: 1200px,
            $font-size-step: 0.3em /* optional parameter, default: 0.1em */
        );
    } 

It basically says:

 - for screen width smaller than 640px I want the font-size to be 1.8em
 - for screen width greater than 1200px I want it to be 3.7em
 - scale the font appropriately in between
 - don't bother changing the font size by less than 0.3em

The SASS code above will be compiled to the following CSS:

    p { font-size: 3.7em; }
    @media all and (max-width: 640px) { p { font-size: 1.8em; } }
    
    @media all and (max-width: 1200px) { p { font-size: 3.7em; } }
    @media all and (max-width: 1103px) { p { font-size: 3.34917em; } }
    @media all and (max-width: 1004px) { p { font-size: 3.0005em; } }
    @media all and (max-width: 904px) { p { font-size: 2.65792em; } }
    @media all and (max-width: 802px) { p { font-size: 2.31846em; } }
    @media all and (max-width: 698px) { p { font-size: 1.9827em; } }

Increase $font-size-step to achieve greater fluency.
