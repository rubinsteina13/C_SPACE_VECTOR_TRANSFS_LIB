# C-library with implementation of the various space-vector transformations

This embedded C-library provides the various types of space-vector transformation:
* [Clarke transformations](https://en.wikipedia.org/wiki/Alpha%E2%80%93beta_transformation)
  * Forward full (ABC to Alpha-Beta)
  * Forward reduce (AB to Alpha-Beta) in case when A + B + C = 0
  * Backward (Inverse) full (Alpha-Beta to ABC)
  * Backward (Inverse) reduce (Alpha-Beta to AB) in case when A + B + C = 0
* [Park transformations](https://en.wikipedia.org/wiki/Direct-quadrature-zero_transformation)
  * Forward (Alpha-Beta to DQ)
  * Backward (Inverse) (DQ to Alpha-Beta)

* Project structure
	* README.md - current file
	* LICENSE - file with license description
  * vector_transfs.h - C-header file with user data types and function prototypes
  * vector_transfs.c - C-source file with firmware functions

# HowToUse (example)

* Example 1

        // updatable user variables:
        float al, be, a, b, c;
				
        // 1st step: create and initialize the global variable of user data structure
        tIFClarke sIFClarke = IF_CLARKE_DEFAULTS;

        // 2nd step: Next code must be executed every time a new calculation of a, b, c is needed
        sIFClarke.fAl = al;               // set Alpha input
        sIFClarke.fBe = be;               // set Beta input
        sIFClarke.m_albe2abc(&sIFClarke); // call the Clarke Inverse Full transformation function
        a = sIFClarke.fA;                 // update the a variable
        b = sIFClarke.fB;                 // update the b variable
        c = sIFClarke.fC;                 // update the c variable

* Example 2


# License
  
[MIT](./LICENSE "License Description")
