
Plain Text (Java), Version 2 Versus 3
by: Keith Fenske, https://kwfenske.github.io/
Wednesday, 4 February 2026

The "Plain Text" Java application is an example of good programming style in
one version (#2) being sacrificed for new features in another version (#3):

- The configuration file for #2 has a simpler syntax that is easier to parse.

- The algorithm for replacing characters in #2 is cleaner and faster, and does
  not require its own data object (i.e., uses only objects that are standard or
  "built in" to the Java run-time environment).

Version 3 did add some features that were important at the time: character
ranges, pre-defined formats, etc. They just aren't worth the mess they made.

The ZIP file for version 2 is kept as a reminder of how good code can go bad
even with the best intentions. The license for #2 was GPLv3+ but can now be
considered the same as #3: Apache 2.0 or GPLv2 or later.

-----
