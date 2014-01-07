stegflag-utils
==============

Tools to make cryptographic hashes and keys more user-friendly

## Concept

In general, people are bad at dealing with large numbers, especially non-decimal ones.  This makes it difficult to get people to perform even basic cryptographic tasks, like checking the MD5 sums of downloaded files.

These tools are attempts to find ways of making these tasks more user-friendly and intuitive.

---

## stegflag-\*

The stegflag tools are inspired by the practice of creating ['steganographic' flags of illegal numbers](http://en.wikipedia.org/wiki/Illegal_number#Flags_and_steganography), and assume five bars of color and an extra 2-digit hexadecimal number can sometimes be preferable to a 32-digit hexadecimal number.

### `stegflag-html`

Usage: `stegflag-html <md5sum>`

Produces an html document containing only an 8-character representation of a flag, based on the md5 sum given in argument.  The first five are the block character █, colored with respective groups of digits in the sum used as hexadecimal color codes.  This covers 30 of the 32 digits, with the last the characters showing the last two digits as an addition to the color bars.

For example, the md5 sum of `stegflag-html` itself is `deb3c138737379239d13e93b46ca9ca0`.  Issuing `stegflag-html deb3c138737379239d13e93b46ca9ca0` produces a file named `deb3c138737379239d13e93b46ca9ca0.html`, which contains this:

    <font color="#deb3c1">█</font>
    <font color="#387373">█</font>
    <font color="#79239d">█</font>
    <font color="#13e93b">█</font>
    <font color="#46ca9c">█</font>+a0

And looks like this:

<font color="#deb3c1">█</font><font color="#387373">█</font><font color="#79239d">█</font><font color="#13e93b">█</font><font color="#46ca9c">█</font>+a0

A copy of `stegflag-html` with an extra empty line has the md5 sum of `eb1075cef1d6b8f00d3add5bc2afeb08`, which can be given to `stegflag-html` to produce this:

<font color="#eb1075">█</font><font color="#cef1d6">█</font><font color="#b8f00d">█</font><font color="#3add5b">█</font><font color="#c2afeb">█</font>+08

### `stegflag-svg`

The `stegflag-svg` scripts does the same thing, except it generates a scalable vector graphics image of the resulting colors.  For example, `stegflag-svg` has an md5 sum of `37717296a557460dd847822045a6b092`, which would produce `37717296a557460dd847822045a6b092.svg`, which would contain this:

    <?xml version="1.0" encoding="UTF-8"?>
    <svg xmlns="http://www.w3.org/2000/svg" width="480" height="288">
    <rect fill="#377172" width="100" height="288" x="0"/>
    <rect fill="#96a557" width="100" height="288" x="100"/>
    <rect fill="#460dd8" width="100" height="288" x="200"/>
    <rect fill="#478220" width="100" height="288" x="300"/>
    <rect fill="#45a6b0" width="100" height="288" x="400"/>
    <text font-size="32" fill="white" font-family="Bitstream Vera Sans" x="388.1" y="269.3">+92<tspan font-size="48"></tspan></text>
    </svg>

And looks like this:

<?xml version="1.0" encoding="UTF-8"?>
<svg xmlns="http://www.w3.org/2000/svg" width="480" height="288">
<rect fill="#377172" width="100" height="288" x="0"/>
<rect fill="#96a557" width="100" height="288" x="100"/>
<rect fill="#460dd8" width="100" height="288" x="200"/>
<rect fill="#478220" width="100" height="288" x="300"/>
<rect fill="#45a6b0" width="100" height="288" x="400"/>
<text font-size="32" fill="white" font-family="Bitstream Vera Sans" x="388.1" y="269.3">+92<tspan font-size="48"></tspan></text>
</svg>

The output of `stegflag-svg` is based on the file [Free-speech-flag.svg](https://commons.wikimedia.org/wiki/File:Free-speech-flag.svg) at [Wikimedia Commons](https://commons.wikimedia.org), which is in the public domain.
