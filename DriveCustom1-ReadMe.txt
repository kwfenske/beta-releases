/*
  Drive Speed #1 - Read/Write Speeds for Disk Drives, Flash Drives
  Written by: Keith Fenske, http://kwfenske.github.io/
  Monday, 31 October 2016
  Java class name: DriveCustom1
  Copyright (c) 2016 by Keith Fenske.  Apache License or GNU GPL.

  *****************************************************************************
  *                                                                           *
  *  DriveCustom1 is a modified version of the DriveSpeed1 Java application,  *
  *  for people who really, really want to test most of the common buffer     *
  *  sizes on their computer and version of Java.  Why?  Higher performance.  *
  *                                                                           *
  *****************************************************************************

  This is a Java 1.4 graphical (GUI) application to test the speed of disk
  drives or flash drives.  Large temporary files are written with all zero
  bytes, then read back.  To get accurate results, files must be bigger than
  the amount of physical memory on your computer (RAM), and should be several
  times bigger, because your computer uses some of its memory as a "disk cache"
  to increase the apparent speed of drives.  Large files minimize the effects
  of cache.  There will be some variation in results, around ten percent over
  minutes and five percent over hours.  Likely factors are:

   1. Hardware speed of disk drive, motherboard, and connections.  CPU speed is
      not a major concern for this program.
   2. Java version and operating system (Linux, MacOS, Windows, etc).
   3. Some file systems (NTFS) may be faster than others (FAT32).  Newly
      formatted disks should be fully written once before testing.
   4. Disk drives may slow down on continuous activity to reduce heat.  Flash
      drives can get slower with usage.  (Repeated testing may degrade flash
      drives.)
   5. Other active programs consume CPU time and disk I/O, including screen
      savers, anti-virus products, and automatic updates.

  When you run this program, choose your options, and click the "Drive Folder"
  button to select a folder (directory) where the program can write one or more
  temporary files.  This can be anywhere on the drive to be tested, where you
  have write access.  Click the "Start" button to begin.  The first test is for
  writing only.  The progress bar above the "Start" button shows how much data
  has been written.  The "Write Speed" box in the bottom right-hand corner
  shows the current write speed, and the final average write speed.  After
  writing is finished, the same file(s) will be read.  Data is not checked for
  being all zero when read, because that would take extra time.  The "Read
  Speed" box in the bottom left-hand corner shows the current read speed, and
  the final average read speed when finished.

  The size of the data buffer is an option.  You rarely need to change this,
  unless you suspect that the computer system is not doing well with a certain
  size.  Buffer size is the number of bytes read or written on each request to
  the system.  Most computers handle a wide range of sizes with equal
  performance.  The default buffer size is generally good.

  Being prompted with a pop-up dialog box is an option, after writing finishes
  and before reading starts.  If your drive is a removable device or on
  removable media, you can remove (eject) the drive by the normal procedure for
  your system, wait a few seconds, reinsert the drive, and continue.  This
  clears the disk cache, and is important for USB thumb drives, which are often
  smaller than the amount of memory on your computer.

  Don't use this program on compressed disks, because zeros are constant and
  highly compressible.  Files with names similar to "ERASE123.DAT" are assumed
  to belong to this program and will be replaced or deleted without notice.
  See also the EraseDisk Java application.

  Apache License or GNU General Public License
  --------------------------------------------
  DriveCustom1 is free software and has been released under the terms and
  conditions of the Apache License (version 2.0 or later) and/or the GNU
  General Public License (GPL, version 2 or later).  This program is
  distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY,
  without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
  PARTICULAR PURPOSE.  See the license(s) for more details.  You should have
  received a copy of the licenses along with this program.  If not, see the
  http://www.apache.org/licenses/ and http://www.gnu.org/licenses/ web pages.

  Graphical Versus Console Application
  ------------------------------------
  The Java command line may contain options for the position and size of the
  application window, and the size of the display font.  See the "-?" option
  for a help summary:

      java  DriveCustom1  -?

  The command line has more options than are visible in the graphical
  interface.  An option such as -u14 or -u16 is recommended because the default
  Java font is too small.

  Restrictions and Limitations
  ----------------------------
  Read speeds will be meaningless if the total number of bytes written is
  smaller than the physical memory (RAM) on a computer, as data may actually be
  "read" from the computer's disk cache and not from the drive.  FAT32-
  formatted volumes (i.e., USB thumb drives) have a maximum size of 4 GB per
  file, unlike exFAT or NTFS.  Windows 2000/XP/Vista/7 tends to misallocate a
  few clusters when large FAT32 volumes are nearly full or files reach their
  maximum size; these show up later as "lost" single-cluster files in CHKDSK.

  Suggestions for New Features
  ----------------------------
  (1) Without a proper way of clearing the disk cache (as with removable
      media), read speeds are often over-inflated.  KF, 2016-11-25.
*/
