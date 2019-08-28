Random number generator (included)
==================================

The task is to:

>State the type of random number generator algorithm used in a language's built-in random number generator. If the language or its immediate libraries don't provide a random number generator, skip this task.
If possible, give a link to a wider [explanation](https://en.wikipedia.org/wiki/List_of_random_number_generators "wp:List of random number generators") of the algorithm used.

Note: the task is *not* to create an RNG, but to report on the languages in-built RNG that would be the most likely RNG used.

The main types of pseudo-random number generator ([PRNG](https://en.wikipedia.org/wiki/PRNG "wp:PRNG")) that are in use are the [Linear Congruential Generator](/wiki/Linear_congruential_generator "Linear congruential generator") ([LCG](https://en.wikipedia.org/wiki/Linear_congruential_generator "wp:Linear congruential generator")), and the Generalized Feedback Shift Register ([GFSR](https://en.wikipedia.org/wiki/Generalised_feedback_shift_register#Non-binary_Galois_LFSR "wp:Generalised feedback shift register")), (of which the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne_twister "wp:Mersenne twister") generator is a subclass). The last main type is where the output of one of the previous ones (typically a Mersenne twister) is fed through a [cryptographic hash function](/wiki/Cryptographic_hash_function "Cryptographic hash function") to maximize unpredictability of individual bits.

Note that neither LCGs nor GFSRs should be used for the most demanding applications (cryptography) without additional steps.

Contents
--------

- [1 8th](#8th)
- [2 ActionScript](#ActionScript)
- [3 Ada](#Ada)
- [4 ALGOL 68](#ALGOL_68)
- [5 AutoHotkey](#AutoHotkey)
- [6 AWK](#AWK)
- [7 BASIC](#BASIC)
- [8 Batch File](#Batch_File)
- [9 BBC BASIC](#BBC_BASIC)
- [10 Befunge](#Befunge)
- [11 C](#C)
- [11.1 C rand()](#C_rand.28.29)
- [1.1.1 BSD rand()](#BSD_rand.28.29)
- [1.1.2 Microsoft rand()](#Microsoft_rand.28.29)
- [11.2 POSIX drand48()](#POSIX_drand48.28.29)
- [12 C++](#C.2B.2B)
- [13 C#](#C.23)
- [14 Clojure](#Clojure)
- [15 CMake](#CMake)
- [16 Common Lisp](#Common_Lisp)
- [17 D](#D)
- [18 Déjà Vu](#D.C3.A9j.C3.A0_Vu)
- [19 Delphi](#Delphi)
- [20 DWScript](#DWScript)
- [21 EchoLisp](#EchoLisp)
- [22 Elena](#Elena)
- [23 Elixir](#Elixir)
- [24 Erlang](#Erlang)
- [25 Euler Math Toolbox](#Euler_Math_Toolbox)
- [26 Factor](#Factor)
- [27 Fortran](#Fortran)
- [28 FreeBASIC](#FreeBASIC)
- [29 Free Pascal](#Free_Pascal)
- [30 FutureBasic](#FutureBasic)
- [31 GAP](#GAP)
- [32 Go](#Go)
- [33 Golfscript](#Golfscript)
- [34 Groovy](#Groovy)
- [35 Haskell](#Haskell)
- [36 Icon and Unicon](#Icon_and_Unicon)
- [37 Io](#Io)
- [38 Inform 7](#Inform_7)
- [39 J](#J)
- [40 Java](#Java)
- [41 JavaScript](#JavaScript)
- [42 Julia](#Julia)
- [43 Kotlin](#Kotlin)
- [44 Lua](#Lua)
- [45 Mathematica](#Mathematica)
- [46 MATLAB](#MATLAB)
- [47 Maxima](#Maxima)
- [48 Modula-3](#Modula-3)
- [49 Nemerle](#Nemerle)
- [50 NetRexx](#NetRexx)
- [51 Nim](#Nim)
- [52 OCaml](#OCaml)
- [53 Octave](#Octave)
- [54 Oz](#Oz)
- [55 PARI/GP](#PARI.2FGP)
- [56 Pascal](#Pascal)
- [57 Perl](#Perl)
- [58 Perl 6](#Perl_6)
- [59 Phix](#Phix)
- [60 PHP](#PHP)
- [61 PicoLisp](#PicoLisp)
- [62 PL/I](#PL.2FI)
- [63 PL/SQL](#PL.2FSQL)
- [63.1 DBMS_RANDOM](#DBMS_RANDOM)
- [63.2 DBMS_CRYPTO](#DBMS_CRYPTO)
- [64 PowerShell](#PowerShell)
- [65 PureBasic](#PureBasic)
- [66 Python](#Python)
- [67 R](#R)
- [68 Racket](#Racket)
- [69 Rascal](#Rascal)
- [70 REXX](#REXX)
- [71 Ring](#Ring)
- [72 Ruby](#Ruby)
- [73 Run BASIC](#Run_BASIC)
- [74 Rust](#Rust)
- [75 Scala](#Scala)
- [76 Seed7](#Seed7)
- [77 Sidef](#Sidef)
- [78 Sparkling](#Sparkling)
- [79 Stata](#Stata)
- [80 Tcl](#Tcl)
- [81 TI-83 BASIC](#TI-83_BASIC)
- [82 TXR](#TXR)
- [83 UNIX Shell](#UNIX_Shell)
- [84 Ursa](#Ursa)
- [85 Ursala](#Ursala)
- [86 XPL0](#XPL0)
- [87 zkl](#zkl)
- [88 ZX Spectrum Basic](#ZX_Spectrum_Basic)

[8th](https://rosettacode.org/wiki/Category:8th)
-----

The default random number generator in 8th is a cryptographically strong one using [Fortuna](https://en.wikipedia.org/wiki/Fortuna_%28PRNG%29), which is seeded from the system's entropy provider. An additional random generator (which is considerably faster) is a [PCG](http://www.pcg-random.org/), though it is not cryptographically strong.

[ActionScript](https://rosettacode.org/wiki/Category:ActionScript)
--------------------------------------------

In both Actionscript 2 and 3, the type of pseudorandom number generator is implementation-defined. This number generator is accessed through the Math.random() function, which returns a double greater than or equal to 0 and less than 1.[[1]](http://livedocs.adobe.com/flash/9.0/ActionScriptLangRefV3/Math.html#random%28%29)[[2]](http://flash-reference.icod.de/Math.html#random%28%29) In Actionscript 2, the global random() function returns an integer greater than or equal to 0 and less than the given argument, but it is deprecated and not recommended.[[3]](http://flash-reference.icod.de/global_functions.html#random())

[Ada](https://rosettacode.org/wiki/Category:Ada)
------------------------------------------------

The Ada standard defines Random Number Generation in Annex A.5.2. There are two kinds of RNGs, Ada.Numerics.Float_Random for floating point values from 0.0 to 1.0, and Ada.Numerics.Discrete_Random for pseudo-random values of enumeration types (including integer types). It provides facilities to initialize the generator and to save it's state.

The standard requires the implementation to uniformly distribute over the range of the result type.

The used algorithm is implementation defined. The standard says: "To enable the user to determine the suitability of the random number generators for the intended application, the implementation shall describe the algorithm used and shall give its period, if known exactly, or a lower bound on the period, if the exact period is unknown."

- [Ada 95 RM - A.5.2 Random Number Generation](http://www.adahome.com/rm95/rm9x-A-05-02.html)
- [Ada 2005 RM - A.5.2 Random Number Generation](http://www.adaic.com/standards/05rm/html/RM-A-5-2.html)
- [Ada 2005 RM - A.5.2 Random Number Generation](http://www.adaic.org/resources/add_content/standards/12rm/html/RM-A-5-2.html)

[ALGOL 68](https://rosettacode.org/wiki/Category:ALGOL_68)
--------

Details of the random number generator are in the Revised Reports sections: 10.2.1. and 10.5.1.

- [10.2\. The standard prelude - 10.2.1\. Environment enquiries](http://vestein.arb-phys.uni-dortmund.de/~wb/RR/rrA2.html)
- [10.5\. The particular preludes and postlude - 10.5.1\. The particular preludes](http://vestein.arb-phys.uni-dortmund.de/~wb/RR/rrA5.html)

```bash
PROC ℒ next random = (REF ℒ INT a)ℒ REAL: ( a :=
¢ the next pseudo-random ℒ integral value after 'a' from a
uniformly distributed sequence on the interval [ℒ 0,ℒ maxint] ¢;

¢ the real value corresponding to 'a' according to some mapping of
integral values [ℒ 0, ℒ max int] into real values [ℒ 0, ℒ 1)
i.e. such that -0 <= x < 1 such that the sequence of real
values so produced preserves the properties of pseudo-randomness
and uniform distribution of the sequence of integral values ¢);

INT ℒ last random := # some initial random number #;
PROC ℒ random = ℒ REAL: ℒ next random(ℒ last random);
```

Note the suitable "next random number" is suggested to be: ( a := ¢ the next pseudo-random ℒ integral value after 'a' from a uniformly distributed sequence on the interval [ℒ 0,ℒ maxint] ¢; ¢ the real value corresponding to 'a' according to some mapping of integral values [ℒ 0, ℒ max int] into real values [ℒ 0, ℒ 1) i.e., such that -0 <= x < 1 such that the sequence of real values so produced preserves the properties of pseudo-randomness and uniform distribution of the sequence of integral values ¢);

Algol68 supports random number generation for all precisions available for the specific implementation. The prefix **ℒ real** indicates all the available precisions. eg **short short real**, **short real**, **real**, **long real**, **long long real** etc

For an ASCII implementation and for **long real** precision these routines would appears as:

```bash
PROC long next random = (REF LONG INT a)LONG REAL: # some suitable next random number #;
INT long last random := # some initial random number #;
PROC long random = LONG REAL: long next random(long last random);
```

[AutoHotkey](https://rosettacode.org/wiki/Category:AutoHotkey)
----------

The built-in command [Random](http://www.autohotkey.com/docs/commands/Random.htm) generates a pseudo-random number using Mersenne Twister "MT19937" (see documentation).

[AWK](https://rosettacode.org/wiki/Category:AWK)
------------------------------------------------

The built-in command "rand" generates a pseudo-random uniform distributed random variable. More information is available from the documentation of [gawk](https://www.gnu.org/software/gawk/manual/html_node/Numeric-Functions.html).

It is important that the RNG is seeded with the funtions "srand", otherwise, the same random number is produced.

Example usage: see [#UNIX_Shell](https://rosettacode.org/wiki/Random_number_generator_(included)#UNIX_Shell)

[BASIC](https://rosettacode.org/wiki/Category:BASIC)
----------------------------------------------------

The RND function generates a pseudo random number greater than or equal to zero, but less than one. The implementation is machine specific based on contents of the ROM and there is no fixed algorithm.

[Batch File](https://rosettacode.org/wiki/Category:Batch_File)
------------------------------------------

Windows batch files can use the `%RANDOM%` pseudo-variable which returns a pseudo-random number between 0 and 32767\. Behind the scenes this is just a call to the C runtime's `rand()` function which uses an LCG in this case:

![equation](https://latex.codecogs.com/gif.latex?X_%7Bn&plus;1%7D%3DX_%7Bn%7D*214013&plus;2531011*%28mod*2%5E%7B15%7D%29)

[BBC BASIC](https://rosettacode.org/wiki/Category:BBC_BASIC)
-----------------

The RND function uses a 33-bit maximal-length Linear Feedback Shift Register (LFSR), with 32-bits being used to provide the result. Hence the sequence length is 2^33-1, during which the value zero is returned once and all non-zero 32-bit values are each returned twice.

[Befunge](https://rosettacode.org/wiki/Category:Befunge)
---------------------------------------

The ? instruction usually uses the random number generator in the interpreter's language. The original interpreter is written in C and uses rand().

[C](https://rosettacode.org/wiki/Category:C)
--------------------------------------------

Standard C has rand(). Some implementations of C have other sources of random numbers, along with rand().

### C rand()

The C standard specifies the interface to the rand() and srand() functions in <stdlib.h>.

- `void srand(unsigned int seed)` begins a new sequence of pseudorandom integers.
- `int rand(void)` returns a pseudorandom integer in the range from 0 to RAND_MAX.
  - RAND_MAX must be at least 32767.

The same seed to srand() reproduces the same sequence. The default seed is 1, when a program calls rand() without calling srand(); so srand(1) reproduces the default sequence. ([n1124.pdf](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1124.pdf))

There are no requirements as to the algorithm to be used for generating the random numbers. All versions of rand() return integers that are uniformly distributed in the interval from 0 to RAND_MAX, but some algorithms have problems in their randomness. For example, the cycle might be too short, or the probabilities might not be independent.

Many popular C libraries implement rand() with a [linear congruential generator](/wiki/Linear_congruential_generator "Linear congruential generator"). The specific multiplier and constant varies by implementation, as does which subset of bits within the result is returned as the random number. These rand() functions should not be used where a good quality random number generator is required.

#### BSD rand()

Among current systems, [BSD](https://rosettacode.org/wiki/BSD) might have the worst algorithm for rand(). BSD rand() sets RAND_MAX to and uses this linear congruential formula:

![formula](https://latex.codecogs.com/gif.latex?state_%7Bn&plus;1%7D%3D1103515245*state_%7Bn%7D&plus;12345*%28mod2%5E%7B31%7D%29)

![formula2](https://latex.codecogs.com/gif.latex?rand_%7Bn%7D%3Dstate_%7Bn%7D)

[FreeBSD](/https://rosettacode.org/mw/index.php?title=FreeBSD&action=edit&redlink=1) switched to a different formula, but [NetBSD](https://rosettacode.org/mw/index.php?title=NetBSD&action=edit&redlink=1) and [OpenBSD](https://rosettacode.org/wiki/OpenBSD) stayed with this formula. ([NetBSD rand.c](http://cvsweb.netbsd.org/bsdweb.cgi/src/lib/libc/stdlib/rand.c?only_with_tag=MAIN), [OpenBSD rand.c](https://www.openbsd.org/cgi-bin/cvsweb/src/lib/libc/stdlib/rand.c))

BSD rand() produces a cycling sequence of only  becomes obvious if one uses the low bit to flip a coin.

```c++
#include <stdio.h>
#include <stdlib.h>

/* Flip a coin, 10 times. */
int
main()
{
    int i;
    srand(time(NULL));
    for (i = 0; i < 10; i++)
        puts((rand() % 2) ? "heads" : "tails");
  return 0;
}
```

If the C compiler uses BSD rand(), then this program has only two possible outputs.

- At even seconds: heads, tails, heads, tails, heads, tails, heads, tails, heads, tails.
- At odd seconds: tails, heads, tails, heads, tails, heads, tails, heads, tails, heads.

The low bit manages a uniform distribution between heads and tails, but it has a period length of only 2: it can only flip a coin 2 times before it must repeat itself. Therefore it must alternate heads and tails. This is not a real coin, and these are not truly random flips.

In general, the low bits from BSD rand() are much less random than the high bits. This defect of BSD rand() is so famous that some programs ignore the low bits from rand().

#### Microsoft rand()[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=14 "Edit section: Microsoft rand()")]

Microsoft sets RAND_MAX to 32767 and uses this linear congruential formula:
]
POSIX adds the drand48() family to <stdlib.h>.

- `void srand48(long seed)` begins a new sequence.
- `double drand48(void)` returns a random double in [0.0, 1.0).
- `long lrand48(void)` returns a random long in [0, 2**31).
- `long mrand48(void)` returns a random long in [-2**31, 2**31).

This family uses a 48-bit linear congruential generator with this formula:

[C++](https://rosettacode.org/wiki/Category:C%2B%2B)
------------------------------------

As part of the C++11 specification the language now includes various forms of random number generation.

While the default engine is implementation specific (ex, unspecified), the following Pseudo-random generators are available in the standard:

- Linear congruential (minstd_rand0, mitd_rand)
- Mersenne twister (mt19937, mt19937_64)
- Subtract with carry (ranlux24_base, raux48_base)
- Discard block (ranlux24, ranlux48)
- Shuffle order (knuth_b)

Additionally, the following distributions are supported:

- Uniform distributions: uniform_int_distribution, uniform_real_distribution
- Bernoulli distributions: bernoulli_distribution, geometric_distribution, binomial_distribution, negative_binomial_distribution
- Poisson distributions: poisson_distribution, gamma_distribution, exponential_distribution, weibull_distribution, extreme_value_distribution
- Normal distributions: normal_distribution, fisher_f_distribution, cauchy_distribution, lognormal_distribution, chi_squared_distribution, student_t_distribution
- Sampling distributions: discrete_distribution, piecewise_linear_distribution, piecewise_constant_distribution

Example of use:

**Works with**: [C++11](/wiki/C%2B%2B11 "C++11")

```c++
#include <iostream>
#include <string>
#include <random>

int main()
{
    std::random_device rd;
    std::uniform_int_distribution<int> dist(1, 10);
    std::mt19937 mt(rd());

    std::cout << "Random Number (hardware): " << dist(rd) << std::endl;
    std::cout << "Mersenne twister (hardware seeded): " << dist(mt) << std::endl;
}
```

[C#](/wiki/Category:C_sharp "Category:C sharp")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=17 "Edit section: C#")]
---------------------------------------------------------------------------------------------------------------------------------------------------------

The .NET Random class says that it uses Knuth's subtractive random number generator algorithm.[[4]](https://msdn.microsoft.com/en-us/library/system.random.aspx#remarksToggle)

[Clojure](/wiki/Category:Clojure "Category:Clojure")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=18 "Edit section: Clojure")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

See Java.

[CMake](/wiki/Category:CMake "Category:CMake")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=19 "Edit section: CMake")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------

CMake has a random *string* generator.

```bash
# Show random integer from 0 to 9999.
[string](https://www.cmake.org/cmake/help/cmake2.6docs.html#command:string)(RANDOM LENGTH 4 ALPHABET 0123456789 number)
[math](https://www.cmake.org/cmake/help/cmake2.6docs.html#command:math)(EXPR number "${number} + 0")  # Remove extra leading 0s.
[message](https://www.cmake.org/cmake/help/cmake2.6docs.html#command:message)(STATUS ${number})
```

The current implementation (in [cmStringCommand.cxx](https://cmake.org/gitweb?p=cmake.git;a=blob;f=Source/cmStringCommand.cxx;hb=HEAD) and [cmSystemTools.cxx](https://cmake.org/gitweb?p=cmake.git;a=blob;f=Source/cmSystemTools.cxx;hb=HEAD)) calls [rand() and srand() from C](/wiki/Random_number_generator_(included)#C "Random number generator (included)"). It picks random letters from the alphabet. The probability of each letter is near *1 ÷ length*, but the implementation uses floating-point arithmetic to map *RAND_MAX + 1* values onto *length* letters, so there is a small modulo bias when *RAND_MAX + 1* is not a multiple of *length*.

CMake 2.6.x has [bug #9851](http://public.kitware.com/Bug/view.php?id=9851); two random strings might be equal because they use the same seed. CMake 2.8.0 fixes this bug by seeding the random generator only once, during the first call to `string(RANDOM ...)`.

CMake 2.8.5 tries a [secure seed](/wiki/Random_number_generator_(device) "Random number generator (device)") (CryptGenRandom or /dev/urandom) or falls back to high-resolution [system time](/wiki/System_time "System time"). Older versions seed the random generator with `time(NULL)`, the current time in seconds.

[Common Lisp](/wiki/Category:Common_Lisp "Category:Common Lisp")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=20 "Edit section: Common Lisp")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The easiest way to generate random numbers in Common Lisp is to use the built-in rand function after seeding the random number generator. For example, the first line seeds the random number generator and the second line generates a number from 0 to 9

```bash
(setf *random-state* (make-random-state t))
(rand 10)
```

[Common Lisp: The Language, 2nd Ed.](https://www.cs.cmu.edu/Groups/AI/html/cltl/clm/node133.html) does not specify a specific random number generator algorithm.

[D](/wiki/Category:D "Category:D")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=21 "Edit section: D")]
-------------------------------------------------------------------------------------------------------------------------------------------

From std.random:

The generators feature a number of well-known and well-documented methods of generating random numbers. An overall fast and reliable means to generate random numbers is the Mt19937 generator, which derives its name from "[Mersenne Twister](https://en.wikipedia.org/wiki/Mersenne_twister) with a period of 2 to the power of 19937". In memory-constrained situations, [linear congruential](https://en.wikipedia.org/wiki/Linear_congruential_generator) generators such as MinstdRand0 and MinstdRand might be useful. The standard library provides an alias Random for whichever generator it considers the most fit for the target environment.

[Déjà Vu](/wiki/Category:D%C3%A9j%C3%A0_Vu "Category:Déjà Vu")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=22 "Edit section: Déjà Vu")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The standard implementation, `[vu](/wiki/Vu "Vu")`, uses a Mersenne twister.

```bash
!print random-int # prints a 32-bit random integer
```

[Delphi](/wiki/Category:Delphi "Category:Delphi")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=23 "Edit section: Delphi")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

According to [Wikipedia](https://en.wikipedia.org/wiki/Linear_congruential_generator#Parameters_in_common_use "wp:Linear congruential generator"), Delphi uses a Linear Congruential Generator.

Random functions:

```bash
 function Random : Extended;
 function Random ( LimitPlusOne  : Integer ) : Integer;
 procedure Randomize;

```

Based on the values given in the wikipedia entry here is a Delphi compatible implementation for use in other pascal dialects.

```bash

{$ifdef fpc}{$mode objfpc}{$endif}

interface

function LCGRandom: extended; overload;inline;
function LCGRandom(const range:longint):longint;overload;inline;

implementation

function IM:cardinal;inline;
begin
  RandSeed := RandSeed * 134775813  + 1;
  Result := RandSeed;
end;

function LCGRandom: extended; overload;inline;
begin
  Result := IM * 2.32830643653870e-10;
end;

function LCGRandom(const range:longint):longint;overload;inline;
begin
  Result := IM * range shr 32;
end;

end.
```

[DWScript](/wiki/Category:DWScript "Category:DWScript")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=24 "Edit section: DWScript")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

DWScript currently uses a 64bit [XorShift](https://en.wikipedia.org/wiki/Xorshift "wp:Xorshift") PRNG, which is a fast and light form of GFSR.

[EchoLisp](/wiki/Category:EchoLisp "Category:EchoLisp")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=25 "Edit section: EchoLisp")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

EchoLisp uses an ARC4 (or RCA4) implementation by David Bau, which replaces the JavaScript Math.random(). Thanks to him. [[5]](https://github.com/davidbau/seedrandom). Some examples :

```bash

(random-seed "albert")
(random) → 0.9672510261922906 ; random float in [0 ... 1[
(random 1000)  → 726  ; random integer in [0 ... 1000 [
(random -1000) → -936 ; random integer in ]-1000 1000[

(lib 'bigint)
(random 1e200) → 48635656441292641677...3917639734865662239925...9490799697903133046309616766848265781368

```

[Elena](/wiki/Category:Elena "Category:Elena")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=26 "Edit section: Elena")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------

ELENA 4.x :

```bash
import extensions;

public program()
{
    console.printLine(randomGenerator.nextReal());
    console.printLine(randomGenerator.eval(0,100))
}
```

```bash
0.706398
46

```

[Elixir](/wiki/Category:Elixir "Category:Elixir")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=27 "Edit section: Elixir")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Elixir does not come with its own module for random number generation. But you can use the appropriate Erlang functions instead. Some examples:

```bash
# Seed the RNG
:random.seed(:erlang.now())

# Integer in the range 1..10
:random.uniform(10)

# Float between 0.0 and 1.0
:random.uniform()
```

For further information, read the Erlang section.

[Erlang](/wiki/Category:Erlang "Category:Erlang")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=28 "Edit section: Erlang")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Random number generator. The method is attributed to B.A. Wichmann and I.D.Hill, in 'An efficient and portable pseudo-random number generator', Journal of Applied Statistics. AS183\. 1982\. Also Byte March 1987.

The current algorithm is a modification of the version attributed to Richard A O'Keefe in the standard Prolog library.

Every time a random number is requested, a state is used to calculate it, and a new state produced. The state can either be implicit (kept in the process dictionary) or be an explicit argument and return value. In this implementation, the state (the type ran()) consists of a tuple of three integers.

It should be noted that this random number generator is not cryptographically strong. If a strong cryptographic random number generator is needed for example crypto:rand_bytes/1 could be used instead.

Seed with a fixed known value triplet A1, A2, A3:

```bash
[random](http://erlang.org/doc/man/random.html):seed(A1, A2, A3)
```

Example with the running time:

```bash
...
{A1,A2,A3} = [erlang](http://erlang.org/doc/man/erlang.html):now(),
[random](http://erlang.org/doc/man/random.html):seed(A1, A2, A3),
...sequence of randoms used
[random](http://erlang.org/doc/man/random.html):seed(A1, A2, A3),
...same sequence of randoms used

```

Get a random float value between 0.0 and 1.0:

```bash

Rfloat = [random](http://erlang.org/doc/man/random.html):uniform(),

```

Get a random integer value between 1 and N (N is an integer >= 1):

```bash

Rint = [random](http://erlang.org/doc/man/random.html):uniform(N),

```

[Euler Math Toolbox](/wiki/Category:Euler_Math_Toolbox "Category:Euler Math Toolbox")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=29 "Edit section: Euler Math Toolbox")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Bays and Durham as describend in Knuth's book.

[Factor](/wiki/Category:Factor "Category:Factor")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=30 "Edit section: Factor")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

The default RNG used when the `random` vocabulary is used, is the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne_twister "wp:Mersenne twister") algorithm [[6]](http://docs.factorcode.org/content/article-random.html). But there are other RNGs available, including [SFMT](https://en.wikipedia.org/wiki/SFMT "wp:SFMT"), the system RNG ([/dev/random](https://en.wikipedia.org/wiki//dev/random "wp:/dev/random") on Unix) and [Blum Blum Shub](https://en.wikipedia.org/wiki/Blum_Blum_Shub "wp:Blum Blum Shub"). It's also very easy to implement your own RNG and integrate it into the system. [[7]](http://docs.factorcode.org/content/article-random-protocol.html)

[Fortran](/wiki/Category:Fortran "Category:Fortran")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=31 "Edit section: Fortran")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

Fortran has intrinsic random_seed() and random_number() subroutines. Used algorithm of the pseudorandom number generator is compiler dependent (not specified in ISO Fortran Standard, see ISO/IEC 1539-1:2010 (E), 13.7.135 RANDOM NUMBER). For algorithm in GNU gfortran see <https://gcc.gnu.org/onlinedocs/gfortran/RANDOM_005fNUMBER.html> Note that with the GNU gfortran compiler program needs to call random_seed with a random PUT= argument to get a pseudorandom number otherwise the sequence always starts with the same number. Intel compiler ifort reinitializes the seed randomly without PUT argument to random value using the system date and time. Here we are seeding random_seed() with some number obtained from the Linux urandom device.

```bash

program rosetta_random
   implicit none

   integer, parameter :: rdp = kind(1.d0)
   real(rdp) :: num
   integer, allocatable :: seed(:)
   integer :: un,n, istat

   call random_seed(size = n)
   allocate(seed(n))

   ! Seed with the OS random number generator
   open(newunit=un, file="/dev/urandom", access="stream", &
   form="unformatted", action="read", status="old", iostat=istat)
   if (istat == 0) then
      read(un) seed
      close(un)
   end if
   call random_seed (put=seed)
   call random_number(num)
   write(*,'(E24.16)') num
end program rosetta_random

```

[FreeBASIC](/wiki/Category:FreeBASIC "Category:FreeBASIC")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=32 "Edit section: FreeBASIC")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

FreeBASIC has a Rnd() function which produces a pseudo-random double precision floating point number in the half-closed interval [0, 1) which can then be easily used to generate pseudo-random numbers (integral or decimal) within any range.

The sequence of pseudo-random numbers can either by seeded by a parameter to the Rnd function itself or to the Randomize statement and, if omitted, uses a seed based on the system timer.

However, a second parameter to the Randomize statement determines which of 5 different algorithms is used to generate the pseudo-random numbers:

1\. Uses the C runtime library's rand() function (based on LCG) which differs depending on the platform but produces a low degree of randomness.

2\. Uses a fast, platform independent, algorithm with 32 bit granularity and a reasonable degree of randomness. The basis of this algorithm is not specified in the language documentation.

3\. Uses the Mersenne Twister algorithm (based on GFSR) which is platform independent, with 32 bit granularity and a high degree of randomness. This is good enough for most non-cryptographic purposes.

4\. Uses a QBASIC compatible algorithm which is platform independent, with 24 bit granularity and a low degree of randomness.

5\. Uses system features (Win32 Crypto API or /dev/urandom device on Linux) to generate pseudo-random numbers, with 32 bit granularity and a very high degree of randomness (cryptographic strength).

A parameter of 0 can also be used (and is the default if omitted) which uses algorithm 3 in the -lang fb dialect, 4 in the -lang qb dialect and 1 in the -lang fblite dialect.

[Free Pascal](/wiki/Category:Free_Pascal "Category:Free Pascal")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=33 "Edit section: Free Pascal")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

FreePascal's function random uses the MersenneTwister (for further details, see the file rtl/inc/system.inc). The random is conform MT19937 and is therefor compatible with e.g. the C++11 MT19937 implementation.

[FutureBasic](/wiki/Category:FutureBasic "Category:FutureBasic")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=34 "Edit section: FutureBasic")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Syntax:

```bash
randomInteger = rnd(expr)

```

This function returns a pseudo-random long integer uniformly distributed in the range 1 through expr. The expr parameter should be greater than 1, and must not exceed 65536\. If the value returned is to be assigned to a 16-bit integer (randomInteger), expr should not exceed 32767\. The actual sequence of numbers returned by rnd depends on the random number generator's "seed" value. (Note that rnd(1) always returns the value 1.)

Syntax:

```bash
random (or randomize) [expr]

```

This statement "seeds" the random number generator: this affects the sequence of values which are subsequently returned by the rnd function and the maybe function. The numbers returned by rnd and maybe are not truly random, but follow a "pseudo-random" sequence which is uniquely determined by the seed number (expr). If you use the same seed number on two different occasions, you'll get the same sequence of "random" numbers both times. When you execute random without any expr parameter, the system's current time is used to seed the random number generator.

Example 1:

```bash
random 375  // using seed number

```

Example 2:

```bash
random      // current system time used as seed

```

Example: To get a random integer between two arbitrary limits min and max, use the following statement. (Note: max - min must be less than or equal to 65536.):

```bash
randomInteger = rnd(max - min + 1) + min - 1

```

To get a random fraction, greater than or equal to zero and less than 1, use this statement:

```bash
frac! = (rnd(65536)-1)/65536.0

```

To get a random long integer in the range 1 through 2,147,483,647, use this statement:

```bash
randomInteger& = ((rnd(65536) - 1)<<15) + rnd(32767)

```

[GAP](/wiki/Category:GAP "Category:GAP")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=35 "Edit section: GAP")]
---------------------------------------------------------------------------------------------------------------------------------------------------

GAP may use two algorithms : MersenneTwister, or algorithm A in section 3.2.2 of TAOCP (which is the default). One may create several *random sources* in parallel, or a global one (based on the TAOCP algorithm).

```bash
# Creating a random source
rs := RandomSource(IsMersenneTwister);

# Generate a random number between 1 and 10
Random(rs, 1, 10);

# Same with default random source
Random(1, 10);
```

One can get random elements from many objects, including lists

```bash

Random([1, 10, 100]);

# Random permutation of 1..200
Random(SymmetricGroup(200));

# Random element of Z/23Z :
Random(Integers mod 23);
```

[Go](/wiki/Category:Go "Category:Go")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=36 "Edit section: Go")]
-----------------------------------------------------------------------------------------------------------------------------------------------

Go has two random number packages in the standard library and another package in the "subrepository."

1. [math/rand](https://golang.org/pkg/math/rand/) in the standard library provides general purpose random number support, implementing some sort of feedback shift register. (It uses a large array commented "feeback register" and has variables named "tap" and "feed.") Comments in the code attribute the algorithm to DP Mitchell and JA Reeds. A little more insight is in [this issue](https://github.com/golang/go/issues/21835) in the Go issue tracker.
2. [crypto/rand](https://golang.org/pkg/crypto/rand/), also in the standard library, says it "implements a cryptographically secure pseudorandom number generator." I think though it should say that it *accesses* a cryptographically secure pseudorandom number generator. It uses `/dev/urandom` on Unix-like systems and the CryptGenRandom API on Windows.
3. [x/exp/rand](https://godoc.org/golang.org/x/exp/rand) implements the Permuted Congruential Generator which is also described in the issue linked above.

[Golfscript](/wiki/Category:Golfscript "Category:Golfscript")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=37 "Edit section: Golfscript")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Golfscript uses Ruby's Mersenne Twister algorithm

`~rand` produces a random integer between 0 and n-1, where n is a positive integer piped into the program

[Groovy](/wiki/Category:Groovy "Category:Groovy")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=38 "Edit section: Groovy")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Same as Java.

[Haskell](/wiki/Category:Haskell "Category:Haskell")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=39 "Edit section: Haskell")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

The [Haskell 98 report](https://www.haskell.org/onlinereport/random.html) specifies an interface for pseudorandom number generation and requires that implementations be minimally statistically robust. It is silent, however, on the choice of algorithm.

[Icon](/wiki/Category:Icon "Category:Icon") and [Unicon](/wiki/Category:Unicon "Category:Unicon")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=40 "Edit section: Icon and Unicon")]
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Icon and Unicon both use the same linear congruential random number generator x := (x * 1103515245 + 453816694) mod 2^31\. Icon uses an initial seed value of 0 and Unicon randomizes the initial seed.

This LCRNG has a number of well documented quirks (see [The Icon Analyst issues #26, 28, 38](https://www.cs.arizona.edu/icon/analyst/ia.htm)) relating to the choices of an even additive and a power of two modulus. This LCRNG produces two independent sequences of length 2^30 one of even numbers the other odd.

Additionally, the**Library:** [Icon Programming Library](/wiki/Category:Icon_Programming_Library "Category:Icon Programming Library")[random](https://www.cs.arizona.edu/icon/library/src/procs/random.icn) provides related procedures including a parametrized LCRNG that defaults to the built-in values.

[Io](/wiki/Category:Io "Category:Io")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=41 "Edit section: Io")]
-----------------------------------------------------------------------------------------------------------------------------------------------

Io's [Random object](http://iolanguage.org/scm/io/docs/reference/index.html#/Math/Random/Random) uses the Mersenne Twister algorithm.

[Inform 7](/wiki/Category:Inform_7 "Category:Inform 7")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=42 "Edit section: Inform 7")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

Inform's random functions are built on the random number generator exposed at runtime by the virtual machine, which is implementation-defined.

[J](/wiki/Category:J "Category:J")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=43 "Edit section: J")]
-------------------------------------------------------------------------------------------------------------------------------------------

By default J's `?` primitive (Roll/Deal) uses the Mersenne twister algorithm, but can be set to use a number of other algorithms as detailed on the [J Dictionary page for Roll/Deal](http://www.jsoftware.com/help/dictionary/d640.htm).

[Java](/wiki/Category:Java "Category:Java")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=44 "Edit section: Java")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

Java's `Random` class uses a [Linear congruential formula](https://en.wikipedia.org/wiki/Linear_congruential_generator "wp:Linear congruential generator"), as described in [its documentation](http://java.sun.com/javase/6/docs/api/java/util/Random.html). The commonly used `Math.random()` uses a `Random` object under the hood.

[JavaScript](/wiki/Category:JavaScript "Category:JavaScript")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=45 "Edit section: JavaScript")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The only built-in random number generation facility is `Math.random()`, which returns a floating-point number greater than or equal to 0 and less than 1, with approximately uniform distribution. The standard (ECMA-262) does not specify what algorithm is to be used.

[Julia](/wiki/Category:Julia "Category:Julia")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=46 "Edit section: Julia")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------

Julia's [built-in random-number generation functions](http://docs.julialang.org/en/latest/stdlib/base/#random-numbers), `rand()` etcetera, use the Mersenne Twister algorithm.

[Kotlin](/wiki/Category:Kotlin "Category:Kotlin")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=47 "Edit section: Kotlin")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

As mentioned in the Java entry, the java.util.Random class uses a linear congruential formula and is not therefore cryptographically secure. However, there is also a derived class, java.security.SecureRandom, which can be used for cryptographic purposes

[Lua](/wiki/Category:Lua "Category:Lua")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=48 "Edit section: Lua")]
---------------------------------------------------------------------------------------------------------------------------------------------------

Lua's `math.random()` is an interface to the C `rand()` function provided by the OS libc; its implementation varies by platform.

[Mathematica](/wiki/Category:Mathematica "Category:Mathematica")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=49 "Edit section: Mathematica")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Mathematica 7, by default, uses an Extended Cellular Automaton method ("ExtendedCA") to generate random numbers. The main PRNG functions are `RandomReal[]` and `RandomInteger[]` You can specify alternative generation methods including the Mersenne Twister and a Linear Congruential Generator (the default earlier versions). Information about random number generation is provided at [Mathematica](https://reference.wolfram.com/mathematica/tutorial/RandomNumberGeneration.html#185956823).

[MATLAB](/wiki/Category:MATLAB "Category:MATLAB")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=50 "Edit section: MATLAB")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

MATLAB uses the Mersenne Twister as its default random number generator. Information about how the "rand()" function is utilized is given at [MathWorks](https://www.mathworks.com/help/techdoc/ref/rand.html).

[Maxima](/wiki/Category:Maxima "Category:Maxima")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=51 "Edit section: Maxima")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Maxima uses a Lisp implementation of the Mersenne Twister. See `? random` for help, or file `share/maxima/5.28.0-2/src/rand-mt19937.lisp` for the source code.

There are also random generators for several [distributions](https://en.wikipedia.org/wiki/Probability_distribution "wp:Probability distribution") in package `distrib` :

- `[random_bernoulli](https://en.wikipedia.org/wiki/Bernoulli_distribution "wp:Bernoulli distribution")`
- `[random_beta](https://en.wikipedia.org/wiki/Beta_distribution "wp:Beta distribution")`
- `[random_binomial](https://en.wikipedia.org/wiki/Binomial_distribution "wp:Binomial distribution")`
- `[random_cauchy](https://en.wikipedia.org/wiki/Cauchy_distribution "wp:Cauchy distribution")`
- `[random_chi2](https://en.wikipedia.org/wiki/Chi-squared_distribution "wp:Chi-squared distribution")`
- `[random_continuous_uniform](https://en.wikipedia.org/wiki/Uniform_distribution_(continuous) "wp:Uniform distribution (continuous)")`
- `[random_discrete_uniform](https://en.wikipedia.org/wiki/Uniform_distribution_(discrete) "wp:Uniform distribution (discrete)")`
- `[random_exp](https://en.wikipedia.org/wiki/Exponential_distribution "wp:Exponential distribution")`
- `[random_f](https://en.wikipedia.org/wiki/F-distribution "wp:F-distribution")`
- `[random_gamma](https://en.wikipedia.org/wiki/Gamma_distribution "wp:Gamma distribution")`
- `[random_general_finite_discrete](https://en.wikipedia.org/wiki/Categorical_distribution "wp:Categorical distribution")`
- `[random_geometric](https://en.wikipedia.org/wiki/Geometric_distribution "wp:Geometric distribution")`
- `[random_gumbel](https://en.wikipedia.org/wiki/Gumbel_distribution "wp:Gumbel distribution")`
- `[random_hypergeometric](https://en.wikipedia.org/wiki/Hypergeometric_distribution "wp:Hypergeometric distribution")`
- `[random_laplace](https://en.wikipedia.org/wiki/Laplace_distribution "wp:Laplace distribution")`
- `[random_logistic](https://en.wikipedia.org/wiki/Logistic_distribution "wp:Logistic distribution")`
- `[random_lognormal](https://en.wikipedia.org/wiki/Lognormal_distribution "wp:Lognormal distribution")`
- `[random_negative_binomial](https://en.wikipedia.org/wiki/Negative_binomial_distribution "wp:Negative binomial distribution")`
- `[random_noncentral_chi2](https://en.wikipedia.org/wiki/Noncentral_chi-squared_distribution "wp:Noncentral chi-squared distribution")`
- `[random_noncentral_student_t](https://en.wikipedia.org/wiki/Noncentral_t-distribution "wp:Noncentral t-distribution")`
- `[random_normal](https://en.wikipedia.org/wiki/Normal_distribution "wp:Normal distribution")`
- `[random_pareto](https://en.wikipedia.org/wiki/Pareto_distribution "wp:Pareto distribution")`
- `[random_poisson](https://en.wikipedia.org/wiki/Poisson_distribution "wp:Poisson distribution")`
- `[random_rayleigh](https://en.wikipedia.org/wiki/Rayleigh_distribution "wp:Rayleigh distribution")`
- `[random_student_t](https://en.wikipedia.org/wiki/Student%27s_t-distribution "wp:Student's t-distribution")`
- `[random_weibull](https://en.wikipedia.org/wiki/Weibull_distribution "wp:Weibull distribution")`

Note: the package `distrib` also has functions starting with `pdf`, `cdf`, `quantile`, `mean`, `var`, `std`, `skewness` or `kurtosis` instead of `random`, except the Cauchy distribution, which does not have [moments](https://en.wikipedia.org/wiki/Moment_(mathematics) "wp:Moment (mathematics)").

[Modula-3](/wiki/Category:Modula-3 "Category:Modula-3")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=52 "Edit section: Modula-3")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

The Random interface in Modula-3 states that it uses "an additive generator based on Knuth's Algorithm 3.2.2A".

[Nemerle](/wiki/Category:Nemerle "Category:Nemerle")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=53 "Edit section: Nemerle")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

Uses .Net Random class; so, as mentioned under C#, above, implements Knuth's subtractive random number generator algorithm. Random class documentation at [MSDN](https://msdn.microsoft.com/en-us/library/system.random.aspx#remarksToggle).

[NetRexx](/wiki/Category:NetRexx "Category:NetRexx")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=54 "Edit section: NetRexx")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

As NetRexx runs in the JVM it simply leverages the Java library. See [Java](#Java) for details of the algorithms used.

[Nim](/wiki/Category:Nim "Category:Nim")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=55 "Edit section: Nim")]
---------------------------------------------------------------------------------------------------------------------------------------------------

There are two PRNGs provided in the standard library:

- **random** : Based on xoroshiro128+ (xor/rotate/shift/rotate), see [here](http://xoroshiro.di.unimi.it/).
- **mersenne** : The Mersenne Twister.

[OCaml](/wiki/Category:OCaml "Category:OCaml")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=56 "Edit section: OCaml")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------

OCaml provides a module called [Random](http://caml.inria.fr/pub/docs/manual-ocaml/libref/Random.html) in its standard library. It used to be a "Linear feedback shift register" pseudo-random number generator (References: Robert Sedgewick, "Algorithms", Addison-Wesley). It is now (as of version 3.12.0) a "lagged-Fibonacci F(55, 24, +) with a modified addition function to enhance the mixing of bits." It passes the Diehard test suite.

[Octave](/wiki/Category:Octave "Category:Octave")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=57 "Edit section: Octave")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

As explained [here](https://www.gnu.org/software/octave/doc/interpreter/Special-Utility-Matrices.html#Special-Utility-Matrices) (see **rand** function), Octave uses the "Mersenne Twister with a period of 2^19937-1".

[Oz](/wiki/Category:Oz "Category:Oz")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=58 "Edit section: Oz")]
-----------------------------------------------------------------------------------------------------------------------------------------------

Oz provides a binding to the C `[rand](https://www.opengroup.org/onlinepubs/000095399/functions/rand.html)` function as `[OS.rand](http://www.mozart-oz.org/home/doc/system/node56.html#label719)`.

[PARI/GP](/wiki/Category:PARI/GP "Category:PARI/GP")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=59 "Edit section: PARI/GP")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

`random` uses Richard Brent's [xorgens](http://wwwmaths.anu.edu.au/~brent/random.html). It's a member of the xorshift class of PRNGs and provides good, fast pseudorandomness (passing the BigCrush test, unlike the Mersenne twister), but it is not cryptographically strong. As implemented in PARI, its period is "at least.

```bash
setrand(3)
random(6)+1
\\ chosen by fair dice roll.
\\ guaranteed to the random.
```

[Pascal](/wiki/Category:Pascal "Category:Pascal")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=60 "Edit section: Pascal")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

See <#Delphi> and [#Free Pascal](#Free_Pascal).

Random functions:

```bash
 function  Random(l: LongInt) : LongInt;
 function  Random : Real;
 procedure Randomize;

```

[Perl](/wiki/Category:Perl "Category:Perl")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=61 "Edit section: Perl")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

Previous to Perl 5.20.0 (May 2014), Perl's `[rand](https://perldoc.perl.org/functions/rand.html)` function will try and call `[drand48](https://www.opengroup.org/onlinepubs/007908775/xsh/drand48.html)`, `[random](https://www.opengroup.org/onlinepubs/000095399/functions/random.html)` or `[rand](https://www.opengroup.org/onlinepubs/000095399/functions/rand.html)` from the C library `[stdlib.h](https://www.opengroup.org/onlinepubs/000095399/basedefs/stdlib.h.html)` in that order.

Beginning with Perl 5.20.0, a drand48() implementation is built into Perl and used on all platforms. The implementation is from FreeBSD and uses a 48-bit linear congruential generator with this formula:

Seeds for drand48 are 32-bit and the initial seed uses 4 bytes of data read from /dev/urandom if possible; a 32-bit mix of various system values otherwise.

Additionally, there are many PRNG's available as modules. Two good Mersenne Twister modules are [Math::Random::MTwist](https://metacpan.org/pod/Math::Random::MTwist) and [Math::Random::MT::Auto](https://metacpan.org/pod/Math::Random::MT::Auto). Modules supporting other distributions can be found in [Math::Random](https://metacpan.org/pod/Math::Random) and [Math::GSL::Randist](https://metacpan.org/pod/Math::GSL::Randist) among others. CSPRNGs include [Bytes::Random::Secure](https://metacpan.org/pod/Bytes::Random::Secure), [Math::Random::Secure](https://metacpan.org/pod/Math::Random::Secure), [Math::Random::ISAAC](https://metacpan.org/pod/Math::Random::ISAAC), and many more.

[Perl 6](/wiki/Category:Perl_6 "Category:Perl 6")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=62 "Edit section: Perl 6")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

The implementation underlying the `rand` function is platform and VM dependent. The JVM backend uses that platform's SecureRandom class.

[Phix](/wiki/Category:Phix "Category:Phix")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=63 "Edit section: Phix")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

The rand(n) routine returns an integer in the range 1 to n, and rnd() returns a floating point number between 0.0 and 1.0\.
In both cases the underlying algorithm is just about as trivial as it can be, certainly not suitable for serious cryptographic work.
There are at least a couple of Mersenne twister components in the archive.

[PHP](/wiki/Category:PHP "Category:PHP")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=64 "Edit section: PHP")]
---------------------------------------------------------------------------------------------------------------------------------------------------

PHP has two random number generators: `[rand](http://us3.php.net/manual/en/function.rand.php)`, which uses the underlying C library's `rand` function; and `[mt_rand](http://us3.php.net/manual/en/function.mt-rand.php)`, which uses the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne_twister "wp:Mersenne twister") algorithm.

[PicoLisp](/wiki/Category:PicoLisp "Category:PicoLisp")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=65 "Edit section: PicoLisp")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

PicoLisp uses a linear congruential generator in the built-in (rand) function, with a multiplier suggested in Knuth's "Seminumerical Algorithms". See the [documentation](http://software-lab.de/doc/refR.html#rand).

[PL/I](/wiki/Category:PL/I "Category:PL/I")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=66 "Edit section: PL/I")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

Values produced by IBM Visualage PL/I compiler built-in random number generator are uniformly distributed between 0 and 1 [0 <= random < 1]

It uses a multiplicative congruential method:

```bash
seed(x) = mod(950706376 * seed(x-1), 2147483647)
random(x) = seed(x) / 2147483647
```

[PL/SQL](/wiki/Category:PL/SQL "Category:PL/SQL")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=67 "Edit section: PL/SQL")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Oracle Database has two packages that can be used for random numbers generation.

### DBMS_RANDOM[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=68 "Edit section: DBMS RANDOM")]

The DBMS_RANDOM package provides a built-in random number generator. This package is not intended for cryptography. It will automatically initialize with the date, user ID, and process ID if no explicit initialization is performed. If this package is seeded twice with the same seed, then accessed in the same way, it will produce the same results in both cases.

```bash
DBMS_RANDOM.RANDOM --produces integers in [-2^^31, 2^^31).
DBMS_RANDOM.VALUE  --produces numbers in [0,1) with 38 digits of precision.
DBMS_RANDOM.NORMAL --produces normal distributed numbers with a mean of 0 and a variance of 1
```

### DBMS_CRYPTO[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=69 "Edit section: DBMS CRYPTO")]

The DBMS_CRYPTO package contains basic cryptographic functions and procedures. The DBMS_CRYPTO.RANDOMBYTES function returns a RAW value containing a cryptographically secure pseudo-random sequence of bytes, which can be used to generate random material for encryption keys. This function is based on the RSA X9.31 PRNG (Pseudo-Random Number Generator).

```
DBMS_CRYPTO.RANDOMBYTES --returns RAW value
DBMS_CRYPTO.RANDOMINTEGER --produces integers in the BINARY_INTEGER datatype
DBMS_CRYPTO.RANDOMNUMBER --produces integer in the NUMBER datatype in the range of [0..2**128-1]
```

[PowerShell](/wiki/Category:PowerShell "Category:PowerShell")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=70 "Edit section: PowerShell")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The [`Get-Random`](https://technet.microsoft.com/en-us/library/dd315402.aspx) cmdlet (part of PowerShell 2) uses the .NET-supplied pseudo-random number generator which uses Knuth's subtractive method; see [C#](#C.23).

[PureBasic](/wiki/Category:PureBasic "Category:PureBasic")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=71 "Edit section: PureBasic")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

PureBasic has two random number generators, `Random()` and `CryptRandom()`. `Random()` uses a RANROT type W generator [[8]](http://www.agner.org/random/theory/chaosran.pdf). `CryptRandom()` uses a very strong PRNG that makes use of a cryptographic safe random number generator for its 'seed', and refreshes the seed if such data is available. The exact method used for `CryptRandom()` is uncertain.

[Python](/wiki/Category:Python "Category:Python")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=72 "Edit section: Python")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Python uses the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne_twister "wp:Mersenne twister") algorithm accessed via the built-in [random module](https://docs.python.org/library/random.html).

[R](/wiki/Category:R "Category:R")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=73 "Edit section: R")]
-------------------------------------------------------------------------------------------------------------------------------------------

For uniform random numbers, R may use Wichmann-Hill, Marsaglia-multicarry, Super-Duper, Mersenne-Twister, or Knuth-TAOCP (both 1997 and 2002 versions), or a user-defined method. The default is Mersenne Twister.

R is able to generate random numbers from a variety of distributions, e.g.

1.  Beta
2.  Binomial
3.  Cauchy
4.  Chi-Squared
5.  Exponential
6.  F
7.  Gamma
8.  Geometric
9.  Hypergeometric
10. Logistic
11. Log Normal
12. Multinomial
13. Negative Binomial
14. Normal
15. Poisson
16. Student t
17. Uniform
18. Weibull

See R help on [Random number generation](http://pbil.univ-lyon1.fr/library/base/html/Random.html), or in the R system type

```
?RNG
help.search("Distribution", package="stats")
```

[Racket](/wiki/Category:Racket "Category:Racket")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=74 "Edit section: Racket")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Racket's random number generator uses a 54-bit version of L'Ecuyer's MRG32k3a algorithm [L'Ecuyer02], as specified in the [docs](https://docs.racket-lang.org/reference/generic-numbers.html#%28def._%28%28quote._~23~25kernel%29._random%29%29). In addition, the "math" library has a bunch of additional [random functions](https://docs.racket-lang.org/math/base.html#%28part._.Random_.Number_.Generation%29).

[Rascal](/wiki/Category:Rascal "Category:Rascal")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=75 "Edit section: Rascal")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Rascal does not have its own arbitrary number generator, but uses the [Java](/wiki/Random_number_generator_(included)#Java "Random number generator (included)") generator. Nonetheless, you can redefine the arbitrary number generator if needed. Rascal has the following functions connected to the random number generator:

```
import util::Math;
arbInt(int limit); // generates an arbitrary integer below limit
arbRat(int limit, int limit); // generates an arbitrary rational number between the limits
arbReal(); // generates an arbitrary real value in the interval [0.0, 1.0]
arbSeed(int seed);
```

The last function can be used to redefine the arbitrary number generator. This function is also used in the getOneFrom() functions.

```
rascal>import List;
ok
rascal>getOneFrom(["zebra", "elephant", "snake", "owl"]);
str: "owl"

```

[REXX](/wiki/Category:REXX "Category:REXX")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=76 "Edit section: REXX")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

The   RANDOM   BIF function is a pseudo-random number (non-negative integer) generator, with a range (spread) limited to   100,000   (but some REXX interpreters support a larger range).

The random numbers generated are not consistent between different REXX interpreters or
even the same REXX interpreters executing on different hardware.

```
     /*(below)  returns a random integer between 100 & 200, inclusive.*/

y = random(100, 200)
```

The random numbers may be repeatable by specifiying a   *seed*   for the   **random**   BIF:

```
call random ,,44    /*the seed in this case is "44". */
  .
  .
  .
y = random(100, 200)
```

Comparison of **random** BIF output for different REXX implementations using a deterministic *seed*.

```
/* REXX ***************************************************************
* 08.09.2013 Walter Pachl
*            Please add the output from other REXXes
* 10.09.2013 Walter Pachl added REXX/TSO
* 01.08.2014 Walter Pachl show what ooRexx supports
**********************************************************************/
Parse Version v
Call random ,,44
ol=v':'
Do i=1 To 10
  ol=ol random(1,10)
  End
If left(v,11)='REXX-ooRexx' Then
  ol=ol random(-999999999,0) /* ooRexx supports negative limits */
Say ol
```

**outputs** from various REXX interpreters:

```
REXX-ooRexx_4.1.3(MT) 6.03 4 Jul 2013: 3 10 6 8 6 9 9 1 1 6
REXX-ooRexx_4.2.0(MT)_32-bit 6.04 22 Feb 2014: 3 10 6 8 6 9 9 1 1 6 -403019526
REXX/Personal 4.00 21 Mar 1992: 7 7 6 7 8 8 5 9 4 7
REXX-r4 4.00 17 Aug 2013: 8 10 7 5 4 2 10 5 2 4
REXX-roo 4.00 28 Jan 2007: 8 10 7 5 4 2 10 5 2 4
REXX-Regina_3.7(MT) 5.00 14 Oct 2012: 10 2 7 10 1 1 8 2 4 1
are the following necessary??
REXX-Regina_3.4p1 (temp bug fix sf.org 1898218)(MT) 5.00 21 Feb 2008: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.2(MT) 5.00 25 Apr 2003: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.3(MT) 5.00 25 Apr 2004: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.4(MT) 5.00 30 Dec 2007: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.5(MT) 5.00 31 Dec 2009: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.6(MT) 5.00 31 Dec 2011: 10 2 7 10 1 1 8 2 4 1
REXX370 3.48 01 May 1992: 8 7 3 1 6 5 5 8 3 2

```

Conclusion: It's not safe to transport a program that uses 'reproducable' use of random-bif (i.e. with a seed) from one environment/implementation to another :-(

[Ring](/wiki/Category:Ring "Category:Ring")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=77 "Edit section: Ring")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

```

nr = 10
for i = 1 to nr
     see random(i) + nl
next

```

[Ruby](/wiki/Category:Ruby "Category:Ruby")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=78 "Edit section: Ruby")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

Ruby's `rand` function currently uses the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne_twister "wp:Mersenne twister") algorithm, as described in [its documentation](https://www.ruby-doc.org/core/classes/Kernel.html#M005974).

[Run BASIC](/wiki/Category:Run_BASIC "Category:Run BASIC")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=79 "Edit section: Run BASIC")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

```
rmd(0)
```
- Return a pseudorandom value between 0 and 1

[Rust](/wiki/Category:Rust "Category:Rust")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=80 "Edit section: Rust")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

Rust's `[rand](https://crates.io/crates/rand)` crate offers several PRNGs. (It is also available via `#![feature(rustc_private)]`). The offering includes some cryptographically secure PRNGs: [ISAAC](https://docs.rs/rand/0.4/rand/isaac/index.html) (both 32 and 64-bit variants) and [ChaCha20](https://docs.rs/rand/0.4/rand/chacha/struct.ChaChaRng.html). `StdRng` is a wrapper of one of those efficient on the current platform. The crate also provides a weak PRNG: [Xorshift128](https://docs.rs/rand/0.4/rand/struct.XorShiftRng.html). It passes diehard but fails TestU01, replacement is being [considered](https://github.com/dhardy/rand/issues/60). `[thread_rng](https://docs.rs/rand/0.4/rand/fn.thread_rng.html)` returns a thread local `StdRng` initialized from the OS. Other PRNGs can be created from the OS or with `thread_rng`.

For any other PRNGs not provided, they merely have to implement the `[Rng](https://docs.rs/rand/0.4/rand/trait.Rng.html)` trait.

[Scala](/wiki/Category:Scala "Category:Scala")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=81 "Edit section: Scala")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------

Scala's `scala.util.Random` class uses a [Linear congruential formula](https://en.wikipedia.org/wiki/Linear_congruential_generator "wp:Linear congruential generator") of the JVM run-time libary, as described in [its documentation](http://java.sun.com/javase/6/docs/api/java/util/Random.html).
An example can be found here:

```
[import](https://scala-lang.org) scala.util.Random

/**
 * Histogram of 200 throws with two dices.
 */
[object](https://scala-lang.org) Throws [extends](https://scala-lang.org) App {
  Stream.continually(Random.nextInt(6) + Random.nextInt(6) + 2)
    .take(200).groupBy(identity).toList.sortBy(_._1)
    .foreach {
      [case](https://scala-lang.org) (a, b) => println(f"$a%2d:" + "X" * b.size)
    }
}
```

<dl>

<dt>Output:</dt>

</dl>

```
 2:XXX
 3:XXXXXXXXX
 4:XXXXXXXXXXXXX
 5:XXXXXXXXXXXXXXXXXXXXXXXXXX
 6:XXXXXXXXXXXXXXXXXXXXXXXXXXXXX
 7:XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
 8:XXXXXXXXXXXXXXXXXXXXXXXXXXXX
 9:XXXXXXXXXXXXXXXXXXXXXXXXXXXX
10:XXXXXXXXXXXXXXXXX
11:XXXXXXXXXXXXXX
12:XX
```

[Seed7](/wiki/Category:Seed7 "Category:Seed7")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=82 "Edit section: Seed7")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------

Seed7 uses a linear congruential generator to compute pseudorandom numbers. Usually random number generators deliver a random value in a fixed range, The Seed7 function [rand(low, high)](http://seed7.sourceforge.net/libraries/integer.htm#rand%28in_integer,in_integer%29) delivers a random number in the requested range [low, high]. Seed7 overloads the *rand* functions for the types char, boolean, [bigInteger](http://seed7.sourceforge.net/libraries/bigint.htm#rand%28in_bigInteger,in_bigInteger%29), [float](http://seed7.sourceforge.net/libraries/float.htm#rand%28ref_float,ref_float%29) and others.

[Sidef](/wiki/Category:Sidef "Category:Sidef")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=83 "Edit section: Sidef")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------

Latest versions of Sidef use the Mersenne Twister algorithm to compute pseudorandom numbers, with different initial seeds (and implementations) for floating-points and integers.

```
say 1.rand          # random float in the interval [0,1)
say 100.irand       # random integer in the interval [0,100)
```

[Sparkling](/wiki/Category:Sparkling "Category:Sparkling")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=84 "Edit section: Sparkling")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Sparkling uses the built-in PRNG of whichever C library implementation the interpreter is compiled against. The Sparkling library functions `random()` and `seed()` map directly to the C standard library functions `rand()` and `srand()` with only one small difference: the return value of `rand()` is divided by `RAND_MAX` so that the generated number is between 0 and 1.

[Stata](/wiki/Category:Stata "Category:Stata")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=85 "Edit section: Stata")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------

See **[set rng](http://www.stata.com/help.cgi?set%20rng)** in Stata help. Stata uses the **[Mersenne Twister](https://en.wikipedia.org/wiki/Mersenne_Twister)** RNG by default, and may use the 32-bit **[KISS](https://en.wikipedia.org/wiki/KISS_(algorithm))** RNG for compatibility with versions earlier than Stata 14.

[Tcl](/wiki/Category:Tcl "Category:Tcl")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=86 "Edit section: Tcl")]
---------------------------------------------------------------------------------------------------------------------------------------------------

Tcl uses a [linear congruential generator](https://en.wikipedia.org/wiki/Linear_congruential_generator "wp:Linear congruential generator") in it's built-in `rand()` function. This is seeded by default from the system time, and kept per-interpreter so different security contexts and different threads can't affect each other's generators (avoiding key deployment issues with the `rand` function from [C](/wiki/C "C")'s math library).

Citations (from Tcl source code):

-   S.K. Park & K.W. Miller, "*Random number generators: good ones are hard to find*," Comm ACM 31(10):1192-1201, Oct 1988
-   W.H. Press & S.A. Teukolsky, "*Portable random number generators*," Computers in Physics 6(5):522-524, Sep/Oct 1992.

[TI-83 BASIC](/wiki/Category:TI-83_BASIC "Category:TI-83 BASIC")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=87 "Edit section: TI-83 BASIC")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

TI-83 uses L'Ecuyer's algorithm to generate random numbers. See [L'Ecuyer's algorithm](https://www.gnu.org/software/gsl/manual/html_node/Random-number-generator-algorithms.html). More explainations can be found in this [paper](http://www.iro.umontreal.ca/~lecuyer/myftp/papers/handstat.pdf).

Random function:

```
rand
```

[TXR](/wiki/Category:TXR "Category:TXR")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=88 "Edit section: TXR")]
---------------------------------------------------------------------------------------------------------------------------------------------------

TXR 50 has a PRNG API, and uses a re-implementation of WELL 512 (avoiding contagion by the "contact authors for commercial uses" virus present in the reference implementation, which attacks BSD licenses). Mersenne Twister was a runner up. There is an object of type random-state, and a global variable *random-state* which holds the default random state. Programs can create random states which are snapshots of existing ones, or which are seeded using an integer value (which can be a bignum). The random function produces a random number modulo some integer value, which can have arbitrary precision. The random-fixnum function produces a non-heap-allocated positive integer with random bits.

[UNIX Shell](/wiki/Category:UNIX_Shell "Category:UNIX Shell")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=89 "Edit section: UNIX Shell")]
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

All **Bourne Shell** clones have a very quick pseudo random number generator.

```
 echo $RANDOM
```

Rach time $RANDOM is referenced it changes it's value (with it's maximum value 32767).

[Ursa](/wiki/Category:Ursa "Category:Ursa")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=90 "Edit section: Ursa")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

Standard Ursa defines the `ursa.util.random` type for random number generators and gives objects of this type a standard interface, but leaves the choice of algorithm up to the implementor.

Cygnus/X Ursa is written in Java and makes calls to java.util.Random, which uses a [Linear congruential formula](https://en.wikipedia.org/wiki/Linear_congruential_generator "wp:Linear congruential generator").

[Ursala](/wiki/Category:Ursala "Category:Ursala")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=91 "Edit section: Ursala")]
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Ursala uses the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne_twister "wp:Mersenne twister") algorithm as implemented by the [Avram](http://www.basis.uklinux.net/avram) run time system for most purposes, except for arbitrary precision floating point random numbers, which are generated by the `urandomb` function from the [mpfr](http://www.mpfr.org) library.

[XPL0](/wiki/Category:XPL0 "Category:XPL0")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=92 "Edit section: XPL0")]
-------------------------------------------------------------------------------------------------------------------------------------------------------

A 31-bit linear congruential generator is used based on an algorithm by Donald Knuth in his book "Art of Computer Programming" Vol 2, 3rd ed. p. 185\. It passes all tests in the Diehard suite. The seed is initialized with the system timer count (at 046C) whenever a program starts. The seed can also be set within a program to give a repeatable sequence of (pseudo) random numbers. Calls to the random number intrinsic return values modulo the argument.

```
include c:\cxpl\codes;  \intrinsic 'code' declarations
int I;
[RanSeed(12345);        \set random number generator seed to 12345
for I:= 1 to 5 do
        [IntOut(0, Ran(1_000_000));  CrLf(0)];
]
```

Output:

```
905495
181227
755989
244883
213142

```

[zkl](/wiki/Category:Zkl "Category:Zkl")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=93 "Edit section: zkl")]
---------------------------------------------------------------------------------------------------------------------------------------------------

zkl uses the Xorshift ([http://en.wikipedia.org/wiki/Xorshift](https://en.wikipedia.org/wiki/Xorshift)) random number generator. It will also, on occasion, read from /dev/urandom.

[ZX Spectrum Basic](/wiki/Category:ZX_Spectrum_Basic "Category:ZX Spectrum Basic")[[edit](/mw/index.php?title=Random_number_generator_(included)&action=edit&section=94 "Edit section: ZX Spectrum Basic")]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The ZX Spectrum uses a Park-Miller (also called a Lehmer) number generator that produces a number between 0 and nearly 1 from a sequence; the RANDOMIZE command can leap to a new entry in the sequence. Multiply the output of RND by 65536 to see the sequence more clearly. The random numbers produced will repeat after 65536 iterations.

Retrieved from "<https://rosettacode.org/mw/index.php?title=Random_number_generator_(included)&oldid=279223>"[Categories](/wiki/Special:Categories "Special:Categories"):

-   [Programming Tasks](/wiki/Category:Programming_Tasks "Category:Programming Tasks")
-   [Solutions by Programming Task](/wiki/Category:Solutions_by_Programming_Task "Category:Solutions by Programming Task")
-   [8th](/wiki/Category:8th "Category:8th")
-   [ActionScript](/wiki/Category:ActionScript "Category:ActionScript")
-   [Ada](/wiki/Category:Ada "Category:Ada")
-   [ALGOL 68](/wiki/Category:ALGOL_68 "Category:ALGOL 68")
-   [AutoHotkey](/wiki/Category:AutoHotkey "Category:AutoHotkey")
-   [AWK](/wiki/Category:AWK "Category:AWK")
-   [BASIC](/wiki/Category:BASIC "Category:BASIC")
-   [Batch File](/wiki/Category:Batch_File "Category:Batch File")
-   [BBC BASIC](/wiki/Category:BBC_BASIC "Category:BBC BASIC")
-   [Befunge](/wiki/Category:Befunge "Category:Befunge")
-   [C](/wiki/Category:C "Category:C")
-   [C++](/wiki/Category:C%2B%2B "Category:C++")
-   [C sharp](/wiki/Category:C_sharp "Category:C sharp")
-   [Clojure](/wiki/Category:Clojure "Category:Clojure")
-   [CMake](/wiki/Category:CMake "Category:CMake")
-   [Common Lisp](/wiki/Category:Common_Lisp "Category:Common Lisp")
-   [D](/wiki/Category:D "Category:D")
-   [Déjà Vu](/wiki/Category:D%C3%A9j%C3%A0_Vu "Category:Déjà Vu")
-   [Delphi](/wiki/Category:Delphi "Category:Delphi")
-   [DWScript](/wiki/Category:DWScript "Category:DWScript")
-   [EchoLisp](/wiki/Category:EchoLisp "Category:EchoLisp")
-   [Elena](/wiki/Category:Elena "Category:Elena")
-   [Elixir](/wiki/Category:Elixir "Category:Elixir")
-   [Erlang](/wiki/Category:Erlang "Category:Erlang")
-   [Euler Math Toolbox](/wiki/Category:Euler_Math_Toolbox "Category:Euler Math Toolbox")
-   [Factor](/wiki/Category:Factor "Category:Factor")
-   [Fortran](/wiki/Category:Fortran "Category:Fortran")
-   [FreeBASIC](/wiki/Category:FreeBASIC "Category:FreeBASIC")
-   [Free Pascal](/wiki/Category:Free_Pascal "Category:Free Pascal")
-   [FutureBasic](/wiki/Category:FutureBasic "Category:FutureBasic")
-   [GAP](/wiki/Category:GAP "Category:GAP")
-   [Go](/wiki/Category:Go "Category:Go")
-   [Golfscript](/wiki/Category:Golfscript "Category:Golfscript")
-   [Groovy](/wiki/Category:Groovy "Category:Groovy")
-   [Haskell](/wiki/Category:Haskell "Category:Haskell")
-   [Icon](/wiki/Category:Icon "Category:Icon")
-   [Unicon](/wiki/Category:Unicon "Category:Unicon")
-   [Icon Programming Library](/wiki/Category:Icon_Programming_Library "Category:Icon Programming Library")
-   [Io](/wiki/Category:Io "Category:Io")
-   [Inform 7](/wiki/Category:Inform_7 "Category:Inform 7")
-   [J](/wiki/Category:J "Category:J")
-   [Java](/wiki/Category:Java "Category:Java")
-   [JavaScript](/wiki/Category:JavaScript "Category:JavaScript")
-   [Julia](/wiki/Category:Julia "Category:Julia")
-   [Kotlin](/wiki/Category:Kotlin "Category:Kotlin")
-   [Lua](/wiki/Category:Lua "Category:Lua")
-   [Mathematica](/wiki/Category:Mathematica "Category:Mathematica")
-   [MATLAB](/wiki/Category:MATLAB "Category:MATLAB")
-   [Maxima](/wiki/Category:Maxima "Category:Maxima")
-   [Modula-3](/wiki/Category:Modula-3 "Category:Modula-3")
-   [Nemerle](/wiki/Category:Nemerle "Category:Nemerle")
-   [NetRexx](/wiki/Category:NetRexx "Category:NetRexx")
-   [Nim](/wiki/Category:Nim "Category:Nim")
-   [OCaml](/wiki/Category:OCaml "Category:OCaml")
-   [Octave](/wiki/Category:Octave "Category:Octave")
-   [Oz](/wiki/Category:Oz "Category:Oz")
-   [PARI/GP](/wiki/Category:PARI/GP "Category:PARI/GP")
-   [Pascal](/wiki/Category:Pascal "Category:Pascal")
-   [Perl](/wiki/Category:Perl "Category:Perl")
-   [Perl 6](/wiki/Category:Perl_6 "Category:Perl 6")
-   [Phix](/wiki/Category:Phix "Category:Phix")
-   [PHP](/wiki/Category:PHP "Category:PHP")
-   [PicoLisp](/wiki/Category:PicoLisp "Category:PicoLisp")
-   [PL/I](/wiki/Category:PL/I "Category:PL/I")
-   [PL/SQL](/wiki/Category:PL/SQL "Category:PL/SQL")
-   [PowerShell](/wiki/Category:PowerShell "Category:PowerShell")
-   [PureBasic](/wiki/Category:PureBasic "Category:PureBasic")
-   [Python](/wiki/Category:Python "Category:Python")
-   [R](/wiki/Category:R "Category:R")
-   [Racket](/wiki/Category:Racket "Category:Racket")
-   [Rascal](/wiki/Category:Rascal "Category:Rascal")
-   [REXX](/wiki/Category:REXX "Category:REXX")
-   [Ring](/wiki/Category:Ring "Category:Ring")
-   [Ruby](/wiki/Category:Ruby "Category:Ruby")
-   [Run BASIC](/wiki/Category:Run_BASIC "Category:Run BASIC")
-   [Rust](/wiki/Category:Rust "Category:Rust")
-   [Scala](/wiki/Category:Scala "Category:Scala")
-   [Seed7](/wiki/Category:Seed7 "Category:Seed7")
-   [Sidef](/wiki/Category:Sidef "Category:Sidef")
-   [Sparkling](/wiki/Category:Sparkling "Category:Sparkling")
-   [Stata](/wiki/Category:Stata "Category:Stata")
-   [Tcl](/wiki/Category:Tcl "Category:Tcl")
-   [TI-83 BASIC](/wiki/Category:TI-83_BASIC "Category:TI-83 BASIC")
-   [TXR](/wiki/Category:TXR "Category:TXR")
-   [UNIX Shell](/wiki/Category:UNIX_Shell "Category:UNIX Shell")
-   [Ursa](/wiki/Category:Ursa "Category:Ursa")
-   [Ursala](/wiki/Category:Ursala "Category:Ursala")
-   [XPL0](/wiki/Category:XPL0 "Category:XPL0")
-   [Zkl](/wiki/Category:Zkl "Category:Zkl")
-   [ZX Spectrum Basic](/wiki/Category:ZX_Spectrum_Basic "Category:ZX Spectrum Basic")
-   [Bc/Omit](/wiki/Category:Bc/Omit "Category:Bc/Omit")
-   [Dc/Omit](/wiki/Category:Dc/Omit "Category:Dc/Omit")
-   [GUISS/Omit](/wiki/Category:GUISS/Omit "Category:GUISS/Omit")
-   [Sed/Omit](/wiki/Category:Sed/Omit "Category:Sed/Omit")
-   [Unlambda/Omit](/wiki/Category:Unlambda/Omit "Category:Unlambda/Omit")
-   [Randomness](/wiki/Category:Randomness "Category:Randomness")

<nav class="navbar navbar-default p-tb " id="p-tb">

-   [What links here](/wiki/Special:WhatLinksHere/Random_number_generator_(included) "A list of all wiki pages that link here [j]")
-   [Related changes](/wiki/Special:RecentChangesLinked/Random_number_generator_(included) "Recent changes in pages linked from this page [k]")
-   [Special pages](/wiki/Special:SpecialPages "A list of all special pages [q]")
-   [Printable version](/mw/index.php?title=Random_number_generator_(included)&printable=yes "Printable version of this page [p]")
-   [Permanent link](/mw/index.php?title=Random_number_generator_(included)&oldid=279223 "Permanent link to this revision of the page")
-   [Page information](/mw/index.php?title=Random_number_generator_(included)&action=info "More information about this page")
-   [Browse properties](/wiki/Special:Browse/Random_number_generator_(included))

</nav>

-   This page was last modified on 18 March 2019, at 15:30.
-   Content is available under [GNU Free Documentation License 1.2](https://www.gnu.org/licenses/fdl-1.2.html) unless otherwise noted.

-   <small>[Privacy policy](/wiki/Rosetta_Code:Privacy_policy "Rosetta Code:Privacy policy")</small>
-   <small>[About Rosetta Code](/wiki/Rosetta_Code:About "Rosetta Code:About")</small>
-   <small>[Disclaimers](/wiki/Rosetta_Code:General_disclaimer "Rosetta Code:General disclaimer")</small>

-   [![GNU Free Documentation License 1.2](/mw/resources/assets/licenses/gnu-fdl.png)](https://www.gnu.org/licenses/fdl-1.2.html)
-   [![Powered by MediaWiki](/mw/resources/assets/poweredby_mediawiki_88x31.png)](//www.mediawiki.org/)
-   [![Powered by Semantic MediaWiki](/mw/extensions/SemanticMediaWiki/includes/../resources/images/smw_button.png)](https://www.semantic-mediawiki.org/wiki/Semantic_MediaWiki)

<script>window.RLQ = window.RLQ || []; window.RLQ.push( function () { mw.loader.state({"user":"ready","user.groups":"ready"});mw.loader.load(["ext.math.scripts","mediawiki.toc","mediawiki.action.view.postEdit","site","mediawiki.user","mediawiki.hidpi","mediawiki.page.ready","mediawiki.searchSuggest","ext.bootstrap.scripts"]); } );</script> <script type="text/javascript">var _gaq = _gaq || []; _gaq.push(["_setAccount", "UA-1219419-1"]); _gaq.push(["_trackPageview"]); (function() { var ga = document.createElement("script"); ga.type = "text/javascript"; ga.async = true; ga.src = ("https:" == document.location.protocol ? "https://ssl" : "http://www") + ".google-analytics.com/ga.js"; var s = document.getElementsByTagName("script")[0]; s.parentNode.insertBefore(ga, s); })();</script> <script>window.RLQ = window.RLQ || []; window.RLQ.push( function () { mw.config.set({"wgBackendResponseTime":897}); } );</script># Random number generator (included)

Random number generator (included)
Task
Random number generator (included)
You are encouraged to solve this task according to the task description, using any language you may know.

The task is to:

    State the type of random number generator algorithm used in a language's built-in random number generator. If the language or its immediate libraries don't provide a random number generator, skip this task.
    If possible, give a link to a wider explanation of the algorithm used.

Note: the task is not to create an RNG, but to report on the languages in-built RNG that would be the most likely RNG used.

The main types of pseudo-random number generator (PRNG) that are in use are the Linear Congruential Generator (LCG), and the Generalized Feedback Shift Register (GFSR), (of which the Mersenne twister generator is a subclass). The last main type is where the output of one of the previous ones (typically a Mersenne twister) is fed through a cryptographic hash function to maximize unpredictability of individual bits.

Note that neither LCGs nor GFSRs should be used for the most demanding applications (cryptography) without additional steps.
Contents

    1 8th
    2 ActionScript
    3 Ada
    4 ALGOL 68
    5 AutoHotkey
    6 AWK
    7 BASIC
    8 Batch File
    9 BBC BASIC
    10 Befunge
    11 C
        11.1 C rand()
            11.1.1 BSD rand()
            11.1.2 Microsoft rand()
        11.2 POSIX drand48()
    12 C++
    13 C#
    14 Clojure
    15 CMake
    16 Common Lisp
    17 D
    18 Déjà Vu
    19 Delphi
    20 DWScript
    21 EchoLisp
    22 Elena
    23 Elixir
    24 Erlang
    25 Euler Math Toolbox
    26 Factor
    27 Fortran
    28 FreeBASIC
    29 Free Pascal
    30 FutureBasic
    31 GAP
    32 Go
    33 Golfscript
    34 Groovy
    35 Haskell
    36 Icon and Unicon
    37 Io
    38 Inform 7
    39 J
    40 Java
    41 JavaScript
    42 Julia
    43 Kotlin
    44 Lua
    45 Mathematica
    46 MATLAB
    47 Maxima
    48 Modula-3
    49 Nemerle
    50 NetRexx
    51 Nim
    52 OCaml
    53 Octave
    54 Oz
    55 PARI/GP
    56 Pascal
    57 Perl
    58 Perl 6
    59 Phix
    60 PHP
    61 PicoLisp
    62 PL/I
    63 PL/SQL
        63.1 DBMS_RANDOM
        63.2 DBMS_CRYPTO
    64 PowerShell
    65 PureBasic
    66 Python
    67 R
    68 Racket
    69 Rascal
    70 REXX
    71 Ring
    72 Ruby
    73 Run BASIC
    74 Rust
    75 Scala
    76 Seed7
    77 Sidef
    78 Sparkling
    79 Stata
    80 Tcl
    81 TI-83 BASIC
    82 TXR
    83 UNIX Shell
    84 Ursa
    85 Ursala
    86 XPL0
    87 zkl
    88 ZX Spectrum Basic

8th

The default random number generator in 8th is a cryptographically strong one using Fortuna, which is seeded from the system's entropy provider. An additional random generator (which is considerably faster) is a PCG, though it is not cryptographically strong.
ActionScript

In both Actionscript 2 and 3, the type of pseudorandom number generator is implementation-defined. This number generator is accessed through the Math.random() function, which returns a double greater than or equal to 0 and less than 1.[1][2] In Actionscript 2, the global random() function returns an integer greater than or equal to 0 and less than the given argument, but it is deprecated and not recommended.[3]
Ada

The Ada standard defines Random Number Generation in Annex A.5.2. There are two kinds of RNGs, Ada.Numerics.Float_Random for floating point values from 0.0 to 1.0, and Ada.Numerics.Discrete_Random for pseudo-random values of enumeration types (including integer types). It provides facilities to initialize the generator and to save it's state.

The standard requires the implementation to uniformly distribute over the range of the result type.

The used algorithm is implementation defined. The standard says: "To enable the user to determine the suitability of the random number generators for the intended application, the implementation shall describe the algorithm used and shall give its period, if known exactly, or a lower bound on the period, if the exact period is unknown."

    Ada 95 RM - A.5.2 Random Number Generation
    Ada 2005 RM - A.5.2 Random Number Generation
    Ada 2005 RM - A.5.2 Random Number Generation

ALGOL 68

Details of the random number generator are in the Revised Reports sections: 10.2.1. and 10.5.1.

    10.2. The standard prelude - 10.2.1. Environment enquiries
    10.5. The particular preludes and postlude - 10.5.1. The particular preludes

PROC ℒ next random = (REF ℒ INT a)ℒ REAL: ( a :=
¢ the next pseudo-random ℒ integral value after 'a' from a
uniformly distributed sequence on the interval [ℒ 0,ℒ maxint] ¢;

¢ the real value corresponding to 'a' according to some mapping of
integral values [ℒ 0, ℒ max int] into real values [ℒ 0, ℒ 1)
i.e. such that -0 <= x < 1 such that the sequence of real
values so produced preserves the properties of pseudo-randomness
and uniform distribution of the sequence of integral values ¢);

INT ℒ last random := # some initial random number #;
PROC ℒ random = ℒ REAL: ℒ next random(ℒ last random);

Note the suitable "next random number" is suggested to be: ( a := ¢ the next pseudo-random ℒ integral value after 'a' from a uniformly distributed sequence on the interval [ℒ 0,ℒ maxint] ¢; ¢ the real value corresponding to 'a' according to some mapping of integral values [ℒ 0, ℒ max int] into real values [ℒ 0, ℒ 1) i.e., such that -0 <= x < 1 such that the sequence of real values so produced preserves the properties of pseudo-randomness and uniform distribution of the sequence of integral values ¢);

Algol68 supports random number generation for all precisions available for the specific implementation. The prefix ℒ real indicates all the available precisions. eg short short real, short real, real, long real, long long real etc

For an ASCII implementation and for long real precision these routines would appears as:

PROC long next random = (REF LONG INT a)LONG REAL: # some suitable next random number #;
INT long last random := # some initial random number #;
PROC long random = LONG REAL: long next random(long last random);

AutoHotkey

The built-in command Random generates a pseudo-random number using Mersenne Twister "MT19937" (see documentation).
AWK

The built-in command "rand" generates a pseudo-random uniform distributed random variable. More information is available from the documentation of gawk.

It is important that the RNG is seeded with the funtions "srand", otherwise, the same random number is produced.

Example usage: see #UNIX_Shell
BASIC

The RND function generates a pseudo random number greater than or equal to zero, but less than one. The implementation is machine specific based on contents of the ROM and there is no fixed algorithm.
Batch File

Windows batch files can use the %RANDOM% pseudo-variable which returns a pseudo-random number between 0 and 32767. Behind the scenes this is just a call to the C runtime's rand() function which uses an LCG in this case:

    X n + 1 = X n ⋅ 214013 + 2531011 ( mod 2 15 ) {\displaystyle X_{n+1}=X_{n}\cdot 214013+2531011{\pmod {2^{15}}}}

BBC BASIC

The RND function uses a 33-bit maximal-length Linear Feedback Shift Register (LFSR), with 32-bits being used to provide the result. Hence the sequence length is 2^33-1, during which the value zero is returned once and all non-zero 32-bit values are each returned twice.
Befunge

The ? instruction usually uses the random number generator in the interpreter's language. The original interpreter is written in C and uses rand().
C

Standard C has rand(). Some implementations of C have other sources of random numbers, along with rand().
C rand()

The C standard specifies the interface to the rand() and srand() functions in <stdlib.h>.

    void srand(unsigned int seed) begins a new sequence of pseudorandom integers.
    int rand(void) returns a pseudorandom integer in the range from 0 to RAND_MAX.
        RAND_MAX must be at least 32767.

The same seed to srand() reproduces the same sequence. The default seed is 1, when a program calls rand() without calling srand(); so srand(1) reproduces the default sequence. (n1124.pdf)

There are no requirements as to the algorithm to be used for generating the random numbers. All versions of rand() return integers that are uniformly distributed in the interval from 0 to RAND_MAX, but some algorithms have problems in their randomness. For example, the cycle might be too short, or the probabilities might not be independent.

Many popular C libraries implement rand() with a linear congruential generator. The specific multiplier and constant varies by implementation, as does which subset of bits within the result is returned as the random number. These rand() functions should not be used where a good quality random number generator is required.
BSD rand()

Among current systems, BSD might have the worst algorithm for rand(). BSD rand() sets RAND_MAX to 2 31 − 1 {\displaystyle 2^{31}-1} and uses this linear congruential formula:

    s t a t e n + 1 = 1103515245 × s t a t e n + 12345 ( mod 2 31 ) {\displaystyle state_{n+1}=1103515245\times state_{n}+12345{\pmod {2^{31}}}}
    r a n d n = s t a t e n {\displaystyle rand_{n}=state_{n}}

FreeBSD switched to a different formula, but NetBSD and OpenBSD stayed with this formula. (NetBSD rand.c, OpenBSD rand.c)

BSD rand() produces a cycling sequence of only 2 31 {\displaystyle 2^{31}} possible states; this is already too short to produce good random numbers. The big problem with BSD rand() is that the low n {\displaystyle n} bits' cycle sequence length is only 2 n {\displaystyle 2^{n}} . (This problem happens because the modulus 2 31 {\displaystyle 2^{31}} is a power of two.) The worst case, when n = 1 {\displaystyle n=1} , becomes obvious if one uses the low bit to flip a coin.

#include <stdio.h>
#include <stdlib.h>

/* Flip a coin, 10 times. */
int
main()
{
	int i;
	srand(time(NULL));
	for (i = 0; i < 10; i++)
		puts((rand() % 2) ? "heads" : "tails");
	return 0;
}

If the C compiler uses BSD rand(), then this program has only two possible outputs.

    At even seconds: heads, tails, heads, tails, heads, tails, heads, tails, heads, tails.
    At odd seconds: tails, heads, tails, heads, tails, heads, tails, heads, tails, heads.

The low bit manages a uniform distribution between heads and tails, but it has a period length of only 2: it can only flip a coin 2 times before it must repeat itself. Therefore it must alternate heads and tails. This is not a real coin, and these are not truly random flips.

In general, the low bits from BSD rand() are much less random than the high bits. This defect of BSD rand() is so famous that some programs ignore the low bits from rand().
Microsoft rand()

Microsoft sets RAND_MAX to 32767 and uses this linear congruential formula:

    s t a t e n + 1 = 214013 × s t a t e n + 2531011 ( mod 2 31 ) {\displaystyle state_{n+1}=214013\times state_{n}+2531011{\pmod {2^{31}}}}
    r a n d n = s e e d n ÷ 2 16 {\displaystyle rand_{n}=seed_{n}\div 2^{16}}

POSIX drand48()

POSIX adds the drand48() family to <stdlib.h>.

    void srand48(long seed) begins a new sequence.
    double drand48(void) returns a random double in [0.0, 1.0).
    long lrand48(void) returns a random long in [0, 2**31).
    long mrand48(void) returns a random long in [-2**31, 2**31).

This family uses a 48-bit linear congruential generator with this formula:

    r n + 1 = 25214903917 × r n + 11 ( mod 2 48 ) {\displaystyle r_{n+1}=25214903917\times r_{n}+11{\pmod {2^{48}}}}

C++

As part of the C++11 specification the language now includes various forms of random number generation.

While the default engine is implementation specific (ex, unspecified), the following Pseudo-random generators are available in the standard:

    Linear congruential (minstd_rand0, minstd_rand)
    Mersenne twister (mt19937, mt19937_64)
    Subtract with carry (ranlux24_base, ranlux48_base)
    Discard block (ranlux24, ranlux48)
    Shuffle order (knuth_b)

Additionally, the following distributions are supported:

    Uniform distributions: uniform_int_distribution, uniform_real_distribution
    Bernoulli distributions: bernoulli_distribution, geometric_distribution, binomial_distribution, negative_binomial_distribution
    Poisson distributions: poisson_distribution, gamma_distribution, exponential_distribution, weibull_distribution, extreme_value_distribution
    Normal distributions: normal_distribution, fisher_f_distribution, cauchy_distribution, lognormal_distribution, chi_squared_distribution, student_t_distribution
    Sampling distributions: discrete_distribution, piecewise_linear_distribution, piecewise_constant_distribution

Example of use:
Works with: C++11

#include <iostream>
#include <string>
#include <random>

int main()
{
    std::random_device rd;
    std::uniform_int_distribution<int> dist(1, 10);
    std::mt19937 mt(rd());

    std::cout << "Random Number (hardware): " << dist(rd) << std::endl;
    std::cout << "Mersenne twister (hardware seeded): " << dist(mt) << std::endl;
}

C#

The .NET Random class says that it uses Knuth's subtractive random number generator algorithm.[4]
Clojure

See Java.
CMake

CMake has a random string generator.

# Show random integer from 0 to 9999.
string(RANDOM LENGTH 4 ALPHABET 0123456789 number)
math(EXPR number "${number} + 0")  # Remove extra leading 0s.
message(STATUS ${number})

The current implementation (in cmStringCommand.cxx and cmSystemTools.cxx) calls rand() and srand() from C. It picks random letters from the alphabet. The probability of each letter is near 1 ÷ length, but the implementation uses floating-point arithmetic to map RAND_MAX + 1 values onto length letters, so there is a small modulo bias when RAND_MAX + 1 is not a multiple of length.

CMake 2.6.x has bug #9851; two random strings might be equal because they use the same seed. CMake 2.8.0 fixes this bug by seeding the random generator only once, during the first call to string(RANDOM ...).

CMake 2.8.5 tries a secure seed (CryptGenRandom or /dev/urandom) or falls back to high-resolution system time. Older versions seed the random generator with time(NULL), the current time in seconds.
Common Lisp

The easiest way to generate random numbers in Common Lisp is to use the built-in rand function after seeding the random number generator. For example, the first line seeds the random number generator and the second line generates a number from 0 to 9

(setf *random-state* (make-random-state t))
(rand 10)

Common Lisp: The Language, 2nd Ed. does not specify a specific random number generator algorithm.
D

From std.random:

The generators feature a number of well-known and well-documented methods of generating random numbers. An overall fast and reliable means to generate random numbers is the Mt19937 generator, which derives its name from "Mersenne Twister with a period of 2 to the power of 19937". In memory-constrained situations, linear congruential generators such as MinstdRand0 and MinstdRand might be useful. The standard library provides an alias Random for whichever generator it considers the most fit for the target environment.
Déjà Vu

The standard implementation, vu, uses a Mersenne twister.

!print random-int # prints a 32-bit random integer

Delphi

According to Wikipedia, Delphi uses a Linear Congruential Generator.

Random functions:

 function Random : Extended;
 function Random ( LimitPlusOne  : Integer ) : Integer;
 procedure Randomize;

Based on the values given in the wikipedia entry here is a Delphi compatible implementation for use in other pascal dialects.


{$ifdef fpc}{$mode objfpc}{$endif}

interface

function LCGRandom: extended; overload;inline;
function LCGRandom(const range:longint):longint;overload;inline;

implementation

function IM:cardinal;inline;
begin
  RandSeed := RandSeed * 134775813  + 1;
  Result := RandSeed;
end;

function LCGRandom: extended; overload;inline;
begin
  Result := IM * 2.32830643653870e-10;
end;

function LCGRandom(const range:longint):longint;overload;inline;
begin
  Result := IM * range shr 32;
end;

end.

DWScript

DWScript currently uses a 64bit XorShift PRNG, which is a fast and light form of GFSR.
EchoLisp

EchoLisp uses an ARC4 (or RCA4) implementation by David Bau, which replaces the JavaScript Math.random(). Thanks to him. [5]. Some examples :


(random-seed "albert")
(random) → 0.9672510261922906 ; random float in [0 ... 1[
(random 1000)  → 726  ; random integer in [0 ... 1000 [
(random -1000) → -936 ; random integer in ]-1000 1000[

(lib 'bigint)
(random 1e200) → 48635656441292641677...3917639734865662239925...9490799697903133046309616766848265781368


Elena

ELENA 4.x :

import extensions;

public program()
{
    console.printLine(randomGenerator.nextReal());
    console.printLine(randomGenerator.eval(0,100))
}

Output:

0.706398
46

Elixir

Elixir does not come with its own module for random number generation. But you can use the appropriate Erlang functions instead. Some examples:


# Seed the RNG
:random.seed(:erlang.now())

# Integer in the range 1..10
:random.uniform(10)

# Float between 0.0 and 1.0
:random.uniform()


For further information, read the Erlang section.
Erlang

Random number generator. The method is attributed to B.A. Wichmann and I.D.Hill, in 'An efficient and portable pseudo-random number generator', Journal of Applied Statistics. AS183. 1982. Also Byte March 1987.

The current algorithm is a modification of the version attributed to Richard A O'Keefe in the standard Prolog library.

Every time a random number is requested, a state is used to calculate it, and a new state produced. The state can either be implicit (kept in the process dictionary) or be an explicit argument and return value. In this implementation, the state (the type ran()) consists of a tuple of three integers.

It should be noted that this random number generator is not cryptographically strong. If a strong cryptographic random number generator is needed for example crypto:rand_bytes/1 could be used instead.

Seed with a fixed known value triplet A1, A2, A3:


random:seed(A1, A2, A3)


Example with the running time:


...
{A1,A2,A3} = erlang:now(),
random:seed(A1, A2, A3),
...sequence of randoms used
random:seed(A1, A2, A3),
...same sequence of randoms used


Get a random float value between 0.0 and 1.0:


Rfloat = random:uniform(),


Get a random integer value between 1 and N (N is an integer >= 1):


Rint = random:uniform(N),


Euler Math Toolbox

Bays and Durham as describend in Knuth's book.
Factor

The default RNG used when the random vocabulary is used, is the Mersenne twister algorithm [6]. But there are other RNGs available, including SFMT, the system RNG (/dev/random on Unix) and Blum Blum Shub. It's also very easy to implement your own RNG and integrate it into the system. [7]
Fortran

Fortran has intrinsic random_seed() and random_number() subroutines. Used algorithm of the pseudorandom number generator is compiler dependent (not specified in ISO Fortran Standard, see ISO/IEC 1539-1:2010 (E), 13.7.135 RANDOM NUMBER). For algorithm in GNU gfortran see https://gcc.gnu.org/onlinedocs/gfortran/RANDOM_005fNUMBER.html Note that with the GNU gfortran compiler program needs to call random_seed with a random PUT= argument to get a pseudorandom number otherwise the sequence always starts with the same number. Intel compiler ifort reinitializes the seed randomly without PUT argument to random value using the system date and time. Here we are seeding random_seed() with some number obtained from the Linux urandom device.


program rosetta_random
   implicit none

   integer, parameter :: rdp = kind(1.d0)
   real(rdp) :: num
   integer, allocatable :: seed(:)
   integer :: un,n, istat

   call random_seed(size = n)
   allocate(seed(n))

   ! Seed with the OS random number generator
   open(newunit=un, file="/dev/urandom", access="stream", &
   form="unformatted", action="read", status="old", iostat=istat)
   if (istat == 0) then
      read(un) seed
      close(un)
   end if
   call random_seed (put=seed)
   call random_number(num)
   write(*,'(E24.16)') num
end program rosetta_random


FreeBASIC

FreeBASIC has a Rnd() function which produces a pseudo-random double precision floating point number in the half-closed interval [0, 1) which can then be easily used to generate pseudo-random numbers (integral or decimal) within any range.

The sequence of pseudo-random numbers can either by seeded by a parameter to the Rnd function itself or to the Randomize statement and, if omitted, uses a seed based on the system timer.

However, a second parameter to the Randomize statement determines which of 5 different algorithms is used to generate the pseudo-random numbers:

1. Uses the C runtime library's rand() function (based on LCG) which differs depending on the platform but produces a low degree of randomness.

2. Uses a fast, platform independent, algorithm with 32 bit granularity and a reasonable degree of randomness. The basis of this algorithm is not specified in the language documentation.

3. Uses the Mersenne Twister algorithm (based on GFSR) which is platform independent, with 32 bit granularity and a high degree of randomness. This is good enough for most non-cryptographic purposes.

4. Uses a QBASIC compatible algorithm which is platform independent, with 24 bit granularity and a low degree of randomness.

5. Uses system features (Win32 Crypto API or /dev/urandom device on Linux) to generate pseudo-random numbers, with 32 bit granularity and a very high degree of randomness (cryptographic strength).

A parameter of 0 can also be used (and is the default if omitted) which uses algorithm 3 in the -lang fb dialect, 4 in the -lang qb dialect and 1 in the -lang fblite dialect.
Free Pascal

FreePascal's function random uses the MersenneTwister (for further details, see the file rtl/inc/system.inc). The random is conform MT19937 and is therefor compatible with e.g. the C++11 MT19937 implementation.
FutureBasic

Syntax:

randomInteger = rnd(expr)

This function returns a pseudo-random long integer uniformly distributed in the range 1 through expr. The expr parameter should be greater than 1, and must not exceed 65536. If the value returned is to be assigned to a 16-bit integer (randomInteger), expr should not exceed 32767. The actual sequence of numbers returned by rnd depends on the random number generator's "seed" value. (Note that rnd(1) always returns the value 1.)

Syntax:

random (or randomize) [expr]

This statement "seeds" the random number generator: this affects the sequence of values which are subsequently returned by the rnd function and the maybe function. The numbers returned by rnd and maybe are not truly random, but follow a "pseudo-random" sequence which is uniquely determined by the seed number (expr). If you use the same seed number on two different occasions, you'll get the same sequence of "random" numbers both times. When you execute random without any expr parameter, the system's current time is used to seed the random number generator.

Example 1:

random 375  // using seed number

Example 2:

random      // current system time used as seed

Example: To get a random integer between two arbitrary limits min and max, use the following statement. (Note: max - min must be less than or equal to 65536.):

randomInteger = rnd(max - min + 1) + min - 1

To get a random fraction, greater than or equal to zero and less than 1, use this statement:

frac! = (rnd(65536)-1)/65536.0

To get a random long integer in the range 1 through 2,147,483,647, use this statement:

randomInteger& = ((rnd(65536) - 1)<<15) + rnd(32767)

GAP

GAP may use two algorithms : MersenneTwister, or algorithm A in section 3.2.2 of TAOCP (which is the default). One may create several random sources in parallel, or a global one (based on the TAOCP algorithm).

# Creating a random source
rs := RandomSource(IsMersenneTwister);

# Generate a random number between 1 and 10
Random(rs, 1, 10);

# Same with default random source
Random(1, 10);

One can get random elements from many objects, including lists


Random([1, 10, 100]);

# Random permutation of 1..200
Random(SymmetricGroup(200));

# Random element of Z/23Z :
Random(Integers mod 23);

Go

Go has two random number packages in the standard library and another package in the "subrepository."

    math/rand in the standard library provides general purpose random number support, implementing some sort of feedback shift register. (It uses a large array commented "feeback register" and has variables named "tap" and "feed.") Comments in the code attribute the algorithm to DP Mitchell and JA Reeds. A little more insight is in this issue in the Go issue tracker.
    crypto/rand, also in the standard library, says it "implements a cryptographically secure pseudorandom number generator." I think though it should say that it accesses a cryptographically secure pseudorandom number generator. It uses /dev/urandom on Unix-like systems and the CryptGenRandom API on Windows.
    x/exp/rand implements the Permuted Congruential Generator which is also described in the issue linked above.

Golfscript

Golfscript uses Ruby's Mersenne Twister algorithm

~rand produces a random integer between 0 and n-1, where n is a positive integer piped into the program
Groovy

Same as Java.
Haskell

The Haskell 98 report specifies an interface for pseudorandom number generation and requires that implementations be minimally statistically robust. It is silent, however, on the choice of algorithm.
Icon and Unicon

Icon and Unicon both use the same linear congruential random number generator x := (x * 1103515245 + 453816694) mod 2^31. Icon uses an initial seed value of 0 and Unicon randomizes the initial seed.

This LCRNG has a number of well documented quirks (see The Icon Analyst issues #26, 28, 38) relating to the choices of an even additive and a power of two modulus. This LCRNG produces two independent sequences of length 2^30 one of even numbers the other odd.
Additionally, the
Library: Icon Programming Library
random provides related procedures including a parametrized LCRNG that defaults to the built-in values.
Io

Io's Random object uses the Mersenne Twister algorithm.
Inform 7

Inform's random functions are built on the random number generator exposed at runtime by the virtual machine, which is implementation-defined.
J

By default J's ? primitive (Roll/Deal) uses the Mersenne twister algorithm, but can be set to use a number of other algorithms as detailed on the J Dictionary page for Roll/Deal.
Java

Java's Random class uses a Linear congruential formula, as described in its documentation. The commonly used Math.random() uses a Random object under the hood.
JavaScript

The only built-in random number generation facility is Math.random(), which returns a floating-point number greater than or equal to 0 and less than 1, with approximately uniform distribution. The standard (ECMA-262) does not specify what algorithm is to be used.
Julia

Julia's built-in random-number generation functions, rand() etcetera, use the Mersenne Twister algorithm.
Kotlin

As mentioned in the Java entry, the java.util.Random class uses a linear congruential formula and is not therefore cryptographically secure. However, there is also a derived class, java.security.SecureRandom, which can be used for cryptographic purposes
Lua

Lua's math.random() is an interface to the C rand() function provided by the OS libc; its implementation varies by platform.
Mathematica

Mathematica 7, by default, uses an Extended Cellular Automaton method ("ExtendedCA") to generate random numbers. The main PRNG functions are RandomReal[] and RandomInteger[] You can specify alternative generation methods including the Mersenne Twister and a Linear Congruential Generator (the default earlier versions). Information about random number generation is provided at Mathematica.
MATLAB

MATLAB uses the Mersenne Twister as its default random number generator. Information about how the "rand()" function is utilized is given at MathWorks.
Maxima

Maxima uses a Lisp implementation of the Mersenne Twister. See ? random for help, or file share/maxima/5.28.0-2/src/rand-mt19937.lisp for the source code.

There are also random generators for several distributions in package distrib :

    random_bernoulli
    random_beta
    random_binomial
    random_cauchy
    random_chi2
    random_continuous_uniform
    random_discrete_uniform
    random_exp
    random_f
    random_gamma
    random_general_finite_discrete
    random_geometric
    random_gumbel
    random_hypergeometric
    random_laplace
    random_logistic
    random_lognormal
    random_negative_binomial
    random_noncentral_chi2
    random_noncentral_student_t
    random_normal
    random_pareto
    random_poisson
    random_rayleigh
    random_student_t
    random_weibull

Note: the package distrib also has functions starting with pdf, cdf, quantile, mean, var, std, skewness or kurtosis instead of random, except the Cauchy distribution, which does not have moments.
Modula-3

The Random interface in Modula-3 states that it uses "an additive generator based on Knuth's Algorithm 3.2.2A".
Nemerle

Uses .Net Random class; so, as mentioned under C#, above, implements Knuth's subtractive random number generator algorithm. Random class documentation at MSDN.
NetRexx

As NetRexx runs in the JVM it simply leverages the Java library. See Java for details of the algorithms used.
Nim

There are two PRNGs provided in the standard library:

    random : Based on xoroshiro128+ (xor/rotate/shift/rotate), see here.
    mersenne : The Mersenne Twister.

OCaml

OCaml provides a module called Random in its standard library. It used to be a "Linear feedback shift register" pseudo-random number generator (References: Robert Sedgewick, "Algorithms", Addison-Wesley). It is now (as of version 3.12.0) a "lagged-Fibonacci F(55, 24, +) with a modified addition function to enhance the mixing of bits." It passes the Diehard test suite.
Octave

As explained here (see rand function), Octave uses the "Mersenne Twister with a period of 2^19937-1".
Oz

Oz provides a binding to the C rand function as OS.rand.
PARI/GP

random uses Richard Brent's xorgens. It's a member of the xorshift class of PRNGs and provides good, fast pseudorandomness (passing the BigCrush test, unlike the Mersenne twister), but it is not cryptographically strong. As implemented in PARI, its period is "at least 2 4096 − 1 {\displaystyle 2^{4096}-1} ".

setrand(3)
random(6)+1
\\ chosen by fair dice roll.
\\ guaranteed to the random.

Pascal

See #Delphi and #Free Pascal.

Random functions:

 function  Random(l: LongInt) : LongInt;
 function  Random : Real;
 procedure Randomize;

Perl

Previous to Perl 5.20.0 (May 2014), Perl's rand function will try and call drand48, random or rand from the C library stdlib.h in that order.

Beginning with Perl 5.20.0, a drand48() implementation is built into Perl and used on all platforms. The implementation is from FreeBSD and uses a 48-bit linear congruential generator with this formula:

    r n + 1 = 25214903917 × r n + 11 ( mod 2 48 ) {\displaystyle r_{n+1}=25214903917\times r_{n}+11{\pmod {2^{48}}}}

Seeds for drand48 are 32-bit and the initial seed uses 4 bytes of data read from /dev/urandom if possible; a 32-bit mix of various system values otherwise.

Additionally, there are many PRNG's available as modules. Two good Mersenne Twister modules are Math::Random::MTwist and Math::Random::MT::Auto. Modules supporting other distributions can be found in Math::Random and Math::GSL::Randist among others. CSPRNGs include Bytes::Random::Secure, Math::Random::Secure, Math::Random::ISAAC, and many more.
Perl 6

The implementation underlying the rand function is platform and VM dependent. The JVM backend uses that platform's SecureRandom class.
Phix

The rand(n) routine returns an integer in the range 1 to n, and rnd() returns a floating point number between 0.0 and 1.0.
In both cases the underlying algorithm is just about as trivial as it can be, certainly not suitable for serious cryptographic work.
There are at least a couple of Mersenne twister components in the archive.
PHP

PHP has two random number generators: rand, which uses the underlying C library's rand function; and mt_rand, which uses the Mersenne twister algorithm.
PicoLisp

PicoLisp uses a linear congruential generator in the built-in (rand) function, with a multiplier suggested in Knuth's "Seminumerical Algorithms". See the documentation.
PL/I

Values produced by IBM Visualage PL/I compiler built-in random number generator are uniformly distributed between 0 and 1 [0 <= random < 1]

It uses a multiplicative congruential method:

seed(x) = mod(950706376 * seed(x-1), 2147483647)
random(x) = seed(x) / 2147483647

PL/SQL

Oracle Database has two packages that can be used for random numbers generation.
DBMS_RANDOM

The DBMS_RANDOM package provides a built-in random number generator. This package is not intended for cryptography. It will automatically initialize with the date, user ID, and process ID if no explicit initialization is performed. If this package is seeded twice with the same seed, then accessed in the same way, it will produce the same results in both cases.

DBMS_RANDOM.RANDOM --produces integers in [-2^^31, 2^^31).
DBMS_RANDOM.VALUE  --produces numbers in [0,1) with 38 digits of precision.
DBMS_RANDOM.NORMAL --produces normal distributed numbers with a mean of 0 and a variance of 1

DBMS_CRYPTO

The DBMS_CRYPTO package contains basic cryptographic functions and procedures. The DBMS_CRYPTO.RANDOMBYTES function returns a RAW value containing a cryptographically secure pseudo-random sequence of bytes, which can be used to generate random material for encryption keys. This function is based on the RSA X9.31 PRNG (Pseudo-Random Number Generator).

DBMS_CRYPTO.RANDOMBYTES --returns RAW value
DBMS_CRYPTO.RANDOMINTEGER --produces integers in the BINARY_INTEGER datatype
DBMS_CRYPTO.RANDOMNUMBER --produces integer in the NUMBER datatype in the range of [0..2**128-1]

PowerShell

The Get-Random cmdlet (part of PowerShell 2) uses the .NET-supplied pseudo-random number generator which uses Knuth's subtractive method; see C#.
PureBasic

PureBasic has two random number generators, Random() and CryptRandom(). Random() uses a RANROT type W generator [8]. CryptRandom() uses a very strong PRNG that makes use of a cryptographic safe random number generator for its 'seed', and refreshes the seed if such data is available. The exact method used for CryptRandom() is uncertain.
Python

Python uses the Mersenne twister algorithm accessed via the built-in random module.
R

For uniform random numbers, R may use Wichmann-Hill, Marsaglia-multicarry, Super-Duper, Mersenne-Twister, or Knuth-TAOCP (both 1997 and 2002 versions), or a user-defined method. The default is Mersenne Twister.

R is able to generate random numbers from a variety of distributions, e.g.

    Beta
    Binomial
    Cauchy
    Chi-Squared
    Exponential
    F
    Gamma
    Geometric
    Hypergeometric
    Logistic
    Log Normal
    Multinomial
    Negative Binomial
    Normal
    Poisson
    Student t
    Uniform
    Weibull

See R help on Random number generation, or in the R system type

?RNG
help.search("Distribution", package="stats")

Racket

Racket's random number generator uses a 54-bit version of L’Ecuyer’s MRG32k3a algorithm [L'Ecuyer02], as specified in the docs. In addition, the "math" library has a bunch of additional random functions.
Rascal

Rascal does not have its own arbitrary number generator, but uses the Java generator. Nonetheless, you can redefine the arbitrary number generator if needed. Rascal has the following functions connected to the random number generator:

import util::Math;
arbInt(int limit); // generates an arbitrary integer below limit
arbRat(int limit, int limit); // generates an arbitrary rational number between the limits
arbReal(); // generates an arbitrary real value in the interval [0.0, 1.0]
arbSeed(int seed);

The last function can be used to redefine the arbitrary number generator. This function is also used in the getOneFrom() functions.

rascal>import List;
ok
rascal>getOneFrom(["zebra", "elephant", "snake", "owl"]);
str: "owl"


REXX

The   RANDOM   BIF function is a pseudo-random number (non-negative integer) generator, with a range (spread) limited to   100,000   (but some REXX interpreters support a larger range).

The random numbers generated are not consistent between different REXX interpreters or
even the same REXX interpreters executing on different hardware.

     /*(below)  returns a random integer between 100 & 200, inclusive.*/

y = random(100, 200)

The random numbers may be repeatable by specifiying a   seed   for the   random   BIF:

call random ,,44    /*the seed in this case is "44". */
  .
  .
  .
y = random(100, 200)

Comparison of random BIF output for different REXX implementations using a deterministic seed.

/* REXX ***************************************************************
* 08.09.2013 Walter Pachl
*            Please add the output from other REXXes
* 10.09.2013 Walter Pachl added REXX/TSO
* 01.08.2014 Walter Pachl show what ooRexx supports
**********************************************************************/
Parse Version v
Call random ,,44
ol=v':'
Do i=1 To 10
  ol=ol random(1,10)
  End
If left(v,11)='REXX-ooRexx' Then
  ol=ol random(-999999999,0) /* ooRexx supports negative limits */
Say ol

outputs from various REXX interpreters:

REXX-ooRexx_4.1.3(MT) 6.03 4 Jul 2013: 3 10 6 8 6 9 9 1 1 6
REXX-ooRexx_4.2.0(MT)_32-bit 6.04 22 Feb 2014: 3 10 6 8 6 9 9 1 1 6 -403019526
REXX/Personal 4.00 21 Mar 1992: 7 7 6 7 8 8 5 9 4 7
REXX-r4 4.00 17 Aug 2013: 8 10 7 5 4 2 10 5 2 4
REXX-roo 4.00 28 Jan 2007: 8 10 7 5 4 2 10 5 2 4
REXX-Regina_3.7(MT) 5.00 14 Oct 2012: 10 2 7 10 1 1 8 2 4 1
are the following necessary??
REXX-Regina_3.4p1 (temp bug fix sf.org 1898218)(MT) 5.00 21 Feb 2008: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.2(MT) 5.00 25 Apr 2003: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.3(MT) 5.00 25 Apr 2004: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.4(MT) 5.00 30 Dec 2007: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.5(MT) 5.00 31 Dec 2009: 10 2 7 10 1 1 8 2 4 1
REXX-Regina_3.6(MT) 5.00 31 Dec 2011: 10 2 7 10 1 1 8 2 4 1
REXX370 3.48 01 May 1992: 8 7 3 1 6 5 5 8 3 2

Conclusion: It's not safe to transport a program that uses 'reproducable' use of random-bif (i.e. with a seed) from one environment/implementation to another :-(
Ring


nr = 10
for i = 1 to nr
     see random(i) + nl
next


Ruby

Ruby's rand function currently uses the Mersenne twister algorithm, as described in its documentation.
Run BASIC

rmd(0)

- Return a pseudorandom value between 0 and 1
Rust

Rust's rand crate offers several PRNGs. (It is also available via #![feature(rustc_private)]). The offering includes some cryptographically secure PRNGs: ISAAC (both 32 and 64-bit variants) and ChaCha20. StdRng is a wrapper of one of those efficient on the current platform. The crate also provides a weak PRNG: Xorshift128. It passes diehard but fails TestU01, replacement is being considered. thread_rng returns a thread local StdRng initialized from the OS. Other PRNGs can be created from the OS or with thread_rng.

For any other PRNGs not provided, they merely have to implement the Rng trait.
Scala

Scala's scala.util.Random class uses a Linear congruential formula of the JVM run-time libary, as described in its documentation.
An example can be found here:

import scala.util.Random

/**
 * Histogram of 200 throws with two dices.
 */
object Throws extends App {
  Stream.continually(Random.nextInt(6) + Random.nextInt(6) + 2)
    .take(200).groupBy(identity).toList.sortBy(_._1)
    .foreach {
      case (a, b) => println(f"$a%2d:" + "X" * b.size)
    }
}

Output:

 2:XXX
 3:XXXXXXXXX
 4:XXXXXXXXXXXXX
 5:XXXXXXXXXXXXXXXXXXXXXXXXXX
 6:XXXXXXXXXXXXXXXXXXXXXXXXXXXXX
 7:XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
 8:XXXXXXXXXXXXXXXXXXXXXXXXXXXX
 9:XXXXXXXXXXXXXXXXXXXXXXXXXXXX
10:XXXXXXXXXXXXXXXXX
11:XXXXXXXXXXXXXX
12:XX

Seed7

Seed7 uses a linear congruential generator to compute pseudorandom numbers. Usually random number generators deliver a random value in a fixed range, The Seed7 function rand(low, high) delivers a random number in the requested range [low, high]. Seed7 overloads the rand functions for the types char, boolean, bigInteger, float and others.
Sidef

Latest versions of Sidef use the Mersenne Twister algorithm to compute pseudorandom numbers, with different initial seeds (and implementations) for floating-points and integers.

say 1.rand          # random float in the interval [0,1)
say 100.irand       # random integer in the interval [0,100)

Sparkling

Sparkling uses the built-in PRNG of whichever C library implementation the interpreter is compiled against. The Sparkling library functions random() and seed() map directly to the C standard library functions rand() and srand() with only one small difference: the return value of rand() is divided by RAND_MAX so that the generated number is between 0 and 1.
Stata

See set rng in Stata help. Stata uses the Mersenne Twister RNG by default, and may use the 32-bit KISS RNG for compatibility with versions earlier than Stata 14.
Tcl

Tcl uses a linear congruential generator in it's built-in rand() function. This is seeded by default from the system time, and kept per-interpreter so different security contexts and different threads can't affect each other's generators (avoiding key deployment issues with the rand function from C's math library).

Citations (from Tcl source code):

    S.K. Park & K.W. Miller, “Random number generators: good ones are hard to find,” Comm ACM 31(10):1192-1201, Oct 1988
    W.H. Press & S.A. Teukolsky, “Portable random number generators,” Computers in Physics 6(5):522-524, Sep/Oct 1992.

TI-83 BASIC

TI-83 uses L'Ecuyer's algorithm to generate random numbers. See L'Ecuyer's algorithm. More explainations can be found in this paper.

Random function:

rand

TXR

TXR 50 has a PRNG API, and uses a re-implementation of WELL 512 (avoiding contagion by the "contact authors for commercial uses" virus present in the reference implementation, which attacks BSD licenses). Mersenne Twister was a runner up. There is an object of type random-state, and a global variable *random-state* which holds the default random state. Programs can create random states which are snapshots of existing ones, or which are seeded using an integer value (which can be a bignum). The random function produces a random number modulo some integer value, which can have arbitrary precision. The random-fixnum function produces a non-heap-allocated positive integer with random bits.
UNIX Shell

All Bourne Shell clones have a very quick pseudo random number generator.

 echo $RANDOM

Rach time $RANDOM is referenced it changes it's value (with it's maximum value 32767).
Ursa

Standard Ursa defines the ursa.util.random type for random number generators and gives objects of this type a standard interface, but leaves the choice of algorithm up to the implementor.

Cygnus/X Ursa is written in Java and makes calls to java.util.Random, which uses a Linear congruential formula.
Ursala

Ursala uses the Mersenne twister algorithm as implemented by the Avram run time system for most purposes, except for arbitrary precision floating point random numbers, which are generated by the urandomb function from the mpfr library.
XPL0

A 31-bit linear congruential generator is used based on an algorithm by Donald Knuth in his book "Art of Computer Programming" Vol 2, 3rd ed. p. 185. It passes all tests in the Diehard suite. The seed is initialized with the system timer count (at 046C) whenever a program starts. The seed can also be set within a program to give a repeatable sequence of (pseudo) random numbers. Calls to the random number intrinsic return values modulo the argument.

include c:\cxpl\codes;  \intrinsic 'code' declarations
int I;
[RanSeed(12345);        \set random number generator seed to 12345
for I:= 1 to 5 do
        [IntOut(0, Ran(1_000_000));  CrLf(0)];
]

Output:

905495
181227
755989
244883
213142

zkl

zkl uses the Xorshift (http://en.wikipedia.org/wiki/Xorshift) random number generator. It will also, on occasion, read from /dev/urandom.
ZX Spectrum Basic
The ZX Spectrum uses a Park-Miller (also called a Lehmer) number generator that produces a number between 0 and nearly 1 from a sequence; the RANDOMIZE command can leap to a new entry in the sequence. Multiply the output of RND by 65536 to see the sequence more clearly. The random numbers produced will repeat after 65536 iterations.
