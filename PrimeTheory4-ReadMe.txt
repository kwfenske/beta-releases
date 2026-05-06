/*
  Prime Theory #4 - Calculate First N Prime Numbers
  Written by: Keith Fenske, http://kwfenske.github.io/
  Friday, 7 May 2004
  Java class name: PrimeTheory4
  Copyright (c) 2004 by Keith Fenske.  Apache License or GNU GPL.

  Calculate the first n prime numbers as efficiently as possible.  This program
  is a modification of PrimeTheory3 that removes many unnecessary steps, such
  as computing the floating-point square root of each number being tested.
  PrimeTheory4 is only about four percent faster than PrimeTheory3, which is
  hardly a significant increase, but the program code is cleaner and makes
  better use of previous results.

  Finding the first n prime numbers is a way of measuring the raw sequential
  speed of a computer.  There are no shortcuts or clever formulas in prime
  number theory.  An obvious algorithm tests each number n by dividing n by all
  numbers from 2 to n-1 and checking for a zero remainder.  Once any factor is
  found (that is, any smaller number that divides evenly without a remainder),
  there is no need to continue: the number n being tested is not prime.  A
  faster algorithm generates a list of known prime numbers and tests each
  number n by dividing n by known prime numbers less than or equal to the
  square root of n.  The speed of the first algorithm is characterized by
  O(n^2) meaning that for large values of n, the computational time is bounded
  by some constant times the square of n.  The speed of the second algorithm
  (implemented here) is better than O(n^1.5).

  The size of our list of known prime numbers is limited to approximately the
  first 5,000,000 primes (a maximum value of 86,028,121), due to the way Java
  1.4 allocates memory on Windows 2000.  Since we only have to test new numbers
  for prime factors up to the square root of the test number, our list can be
  used to test much larger numbers with almost double the number of digits as
  the largest prime factor in the list (a range of 7,400,837,602,790,641).
  Note that the frequency of prime numbers slowly decreases as n increases (see
  following table).

  The milestone prime numbers are:

                1st =              2
               10th =             29
              100th =            541
            1,000th =          7,919
           10,000th =        104,729

          100,000th =      1,299,709 (1.43 seconds on a Pentium 4 at 2.4 GHz)
        1,000,000th =     15,485,863 (33.0 seconds)
       10,000,000th =    179,424,673 (14.8 minutes)
      100,000,000th =  2,038,074,743 (6.97 hours)
    1,000,000,000th = 22,801,763,489 (8.55 days)

  largest  7-bit prime:           127 (31st) = 0x7F
  largest  8-bit prime:           251 (54th) = 0xFB
  largest 15-bit prime:        32,749 (3,512th) = 0x7FED
  largest 16-bit prime:        65,521 (6,542nd) = 0xFFF1
  largest 31-bit prime: 2,147,483,647 (105,097,565th) = 0x7FFFFFFF
  largest 32-bit prime: 4,294,967,291 (203,280,221st) = 0xFFFFFFFB

  To obtain the speeds listed above, this program was modified to print only
  every 10,000th prime number (an arbitrary figure chosen just to show that the
  program was still running).  Otherwise the speeds would be about ten times
  slower because of formatting the System.out.println calls and waiting for the
  I/O text to scroll.  The formatting is a constant amount of time for each
  prime number, but the I/O waits introduce delays that are not related to the
  amount of work being done by the algorithm.

  When we talk about an efficient algorithm, we don't always mean the fastest
  program in terms of CPU time.  In addition to speed, this program must also
  satisfy the following conditions:

  (1) be simple and easy to understand;
  (2) handle very large numbers; and
  (3) produce correct results without error.

  A problem with Big-O notation is revealed when the execution time for this
  program grows faster than expected for large numbers.  Big-O notation assumes
  that the basic unit of measurement stays constant; for this algorithm, that
  is the execution time for integer division.  Hardware integer division
  actually takes longer (more machine cycles) for larger integers.  Further,
  even though Java may have 64-bit "long" integers, the underlying computer
  hardware may not, in which case 64-bit division is emulated with multiple
  32-bit division.

  Apache License or GNU General Public License
  --------------------------------------------
  PrimeTheory4 is free software and has been released under the terms and
  conditions of the Apache License (version 2.0 or later) and/or the GNU
  General Public License (GPL, version 2 or later).  This program is
  distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY,
  without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
  PARTICULAR PURPOSE.  See the license(s) for more details.  You should have
  received a copy of the licenses along with this program.  If not, see the
  http://www.apache.org/licenses/ and http://www.gnu.org/licenses/ web pages.
*/
