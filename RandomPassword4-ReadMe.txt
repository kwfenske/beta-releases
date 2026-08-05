/*
  Random Password #4 - Generate Random Passwords Given Alphabet, Length
  Written by: Keith Fenske, http://kwfenske.github.io/
  Friday, 25 October 2024
  Java class name: RandomPassword4
  Copyright (c) 2024 by Keith Fenske.  Apache License or GNU GPL.

  This is a Java 5.0 application to generate random passwords given an alphabet
  (list of available characters), the length of each password (in characters),
  and the number of passwords required.  The default alphabet uses letters and
  digits that most people can distinguish when written down on a piece of
  paper.  This alphabet does not have to be unique, and may repeat characters
  so they are more likely to appear.

  Our minds look for patterns in random data.  What we see is not always there.
  Duplicates make us think data can not be random.  In fact, the opposite is
  true.  If you generate passwords of length 10 from an alphabet of 30
  characters, then on average, one in four passwords will have an identical
  pair.  Simply ignore passwords that you don't like.

  Apache License or GNU General Public License
  --------------------------------------------
  RandomPassword4 is free software and has been released under the terms and
  conditions of the Apache License (version 2.0 or later) and/or the GNU
  General Public License (GPL, version 2 or later).  This program is
  distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY,
  without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
  PARTICULAR PURPOSE.  See the license(s) for more details.  You should have
  received a copy of the licenses along with this program.  If not, see the
  http://www.apache.org/licenses/ and http://www.gnu.org/licenses/ web pages.

  Graphical Versus Console Application
  ------------------------------------
  The Java command line may contain options or a desired number of passwords.
  If the command line does not say how many passwords to generate, then this
  program runs as a graphical or "GUI" application with the usual dialog boxes
  and windows.  See the "-?" option for a help summary:

      java  RandomPassword4  -?

  The command line has more options than are visible in the graphical
  interface.  An option such as -u16 or -u18 is recommended for the font size.

  Restrictions and Limitations
  ----------------------------
  Characters above U+FFFF in the Unicode standard are handled correctly, unlike
  the previous Java 1.4 version of this program.
*/
