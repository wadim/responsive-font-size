responsive-font-size
====================

A SASS mixin to ease creating layouts which scale font-size based on screen width. A pure (S)CSS2 solution. No JS or CSS3 support required.

Usage:

@import "responsive-font-size";

p {
    @include responsive-font-size (
        $min-font-size: 1.8em,
        $max-font-size: 3.7em,
        $scale-factor: 1 / 300
    );
}