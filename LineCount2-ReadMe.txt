/*
  Line Count #2 - Count Number of Characters and Lines in Text File
  Written by: Keith Fenske, http://kwfenske.github.io/
  Monday, 27 July 2026
  Java class name: LineCount2
  Copyright (c) 2026 by Keith Fenske.  Apache License or GNU GPL.

  This is a Java 5.0 console application to count the number of characters and
  lines in a plain text file such as source code.  Put one or more file names
  on the command line:

    java  LineCount2  x.txt

  Text lines may end with a carriage return (CR or 0x0D), a line feed (LF or
  0x0A), or CR followed by LF.  Having LF by itself is more commonly called a
  "newline" character or NL.  If a file has a different character set than your
  system's default encoding, you should put the name of a character set as the
  "-e" option.  For example, UTF-8 is very popular with web pages:

    java  LineCount2  -eUTF-8  x.txt

  There is no graphical interface (GUI) for this program; it must be run from a
  command prompt, command shell, or terminal window.  See the "-?" option for a
  help summary.

  Apache License or GNU General Public License
  --------------------------------------------
  LineCount2 is free software and has been released under the terms and
  conditions of the Apache License (version 2.0 or later) and/or the GNU
  General Public License (GPL, version 2 or later).  This program is
  distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY,
  without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
  PARTICULAR PURPOSE.  See the license(s) for more details.  You should have
  received a copy of the licenses along with this program.  If not, see the
  http://www.apache.org/licenses/ and http://www.gnu.org/licenses/ web pages.

  Restrictions and Limitations
  ----------------------------
  Characters above U+FFFF in the Unicode standard are counted correctly, unlike
  the previous Java 1.4 version of this program.
*/

> java  LineCount2  -?

Count Number of Characters and Lines in Text File - by: Keith Fenske

This is a Java console application to count the number of characters and lines
in a plain text file such as source code.

  java  LineCount2  [options]  fileNames

You may give options on the command line:

  -? = -help = show summary of command-line syntax
  -e# = character set name or text encoding; default is local system;
      example: -eUTF-8
  -m# = output message format, arbitrary index from 0 to 999 (customized)

Copyright (c) 2026 by Keith Fenske.  Apache License or GNU GPL.
