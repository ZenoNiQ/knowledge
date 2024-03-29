# Random number generator (included)

The task is to:

> State the type of random number generator algorithm used in a language's built-in random number generator. If the language or its immediate libraries don't provide a random number generator, skip this task. If possible, give a link to a wider [explanation](https://en.wikipedia.org/wiki/List\_of\_random\_number\_generators) of the algorithm used.

Note: the task is _not_ to create an RNG, but to report on the languages in-built RNG that would be the most likely RNG used.

The main types of pseudo-random number generator ([PRNG](https://en.wikipedia.org/wiki/PRNG)) that are in use are the [Linear Congruential Generator](../wiki/Linear\_congruential\_generator/) ([LCG](https://en.wikipedia.org/wiki/Linear\_congruential\_generator)), and the Generalized Feedback Shift Register ([GFSR](https://en.wikipedia.org/wiki/Generalised\_feedback\_shift\_register#Non-binary\_Galois\_LFSR)), (of which the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne\_twister) generator is a subclass). The last main type is where the output of one of the previous ones (typically a Mersenne twister) is fed through a [cryptographic hash function](../wiki/Cryptographic\_hash\_function/) to maximize unpredictability of individual bits.

Note that neither LCGs nor GFSRs should be used for the most demanding applications (cryptography) without additional steps.

## Contents

* [1 8th](random-number-generator-included.md#8th)
* [2 ActionScript](random-number-generator-included.md#ActionScript)
* [3 Ada](random-number-generator-included.md#Ada)
* [4 ALGOL 68](random-number-generator-included.md#ALGOL\_68)
* [5 AutoHotkey](random-number-generator-included.md#AutoHotkey)
* [6 AWK](random-number-generator-included.md#AWK)
* [7 BASIC](random-number-generator-included.md#BASIC)
* [8 Batch File](random-number-generator-included.md#Batch\_File)
* [9 BBC BASIC](random-number-generator-included.md#BBC\_BASIC)
* [10 Befunge](random-number-generator-included.md#Befunge)
* [11 C](random-number-generator-included.md#C)
* [11.1 C rand()](random-number-generator-included.md#C\_rand.28.29)
* [1.1.1 BSD rand()](random-number-generator-included.md#BSD\_rand.28.29)
* [1.1.2 Microsoft rand()](random-number-generator-included.md#Microsoft\_rand.28.29)
* [11.2 POSIX drand48()](random-number-generator-included.md#POSIX\_drand48.28.29)
* [12 C++](random-number-generator-included.md#C.2B.2B)
* [13 C#](random-number-generator-included.md#C.23)
* [14 Clojure](random-number-generator-included.md#Clojure)
* [15 CMake](random-number-generator-included.md#CMake)
* [16 Common Lisp](random-number-generator-included.md#Common\_Lisp)
* [17 D](random-number-generator-included.md#D)
* [18 Déjà Vu](random-number-generator-included.md#D.C3.A9j.C3.A0\_Vu)
* [19 Delphi](random-number-generator-included.md#Delphi)
* [20 DWScript](random-number-generator-included.md#DWScript)
* [21 EchoLisp](random-number-generator-included.md#EchoLisp)
* [22 Elena](random-number-generator-included.md#Elena)
* [23 Elixir](random-number-generator-included.md#Elixir)
* [24 Erlang](random-number-generator-included.md#Erlang)
* [25 Euler Math Toolbox](random-number-generator-included.md#Euler\_Math\_Toolbox)
* [26 Factor](random-number-generator-included.md#Factor)
* [27 Fortran](random-number-generator-included.md#Fortran)
* [28 FreeBASIC](random-number-generator-included.md#FreeBASIC)
* [29 Free Pascal](random-number-generator-included.md#Free\_Pascal)
* [30 FutureBasic](random-number-generator-included.md#FutureBasic)
* [31 GAP](random-number-generator-included.md#GAP)
* [32 Go](random-number-generator-included.md#Go)
* [33 Golfscript](random-number-generator-included.md#Golfscript)
* [34 Groovy](random-number-generator-included.md#Groovy)
* [35 Haskell](random-number-generator-included.md#Haskell)
* [36 Icon and Unicon](random-number-generator-included.md#Icon\_and\_Unicon)
* [37 Io](random-number-generator-included.md#Io)
* [38 Inform 7](random-number-generator-included.md#Inform\_7)
* [39 J](random-number-generator-included.md#J)
* [40 Java](random-number-generator-included.md#Java)
* [41 JavaScript](random-number-generator-included.md#JavaScript)
* [42 Julia](random-number-generator-included.md#Julia)
* [43 Kotlin](random-number-generator-included.md#Kotlin)
* [44 Lua](random-number-generator-included.md#Lua)
* [45 Mathematica](random-number-generator-included.md#Mathematica)
* [46 MATLAB](random-number-generator-included.md#MATLAB)
* [47 Maxima](random-number-generator-included.md#Maxima)
* [48 Modula-3](random-number-generator-included.md#Modula-3)
* [49 Nemerle](random-number-generator-included.md#Nemerle)
* [50 NetRexx](random-number-generator-included.md#NetRexx)
* [51 Nim](random-number-generator-included.md#Nim)
* [52 OCaml](random-number-generator-included.md#OCaml)
* [53 Octave](random-number-generator-included.md#Octave)
* [54 Oz](random-number-generator-included.md#Oz)
* [55 PARI/GP](random-number-generator-included.md#PARI.2FGP)
* [56 Pascal](random-number-generator-included.md#Pascal)
* [57 Perl](random-number-generator-included.md#Perl)
* [58 Perl 6](random-number-generator-included.md#Perl\_6)
* [59 Phix](random-number-generator-included.md#Phix)
* [60 PHP](random-number-generator-included.md#PHP)
* [61 PicoLisp](random-number-generator-included.md#PicoLisp)
* [62 PL/I](random-number-generator-included.md#PL.2FI)
* [63 PL/SQL](random-number-generator-included.md#PL.2FSQL)
* [63.1 DBMS\_RANDOM](random-number-generator-included.md#DBMS\_RANDOM)
* [63.2 DBMS\_CRYPTO](random-number-generator-included.md#DBMS\_CRYPTO)
* [64 PowerShell](random-number-generator-included.md#PowerShell)
* [65 PureBasic](random-number-generator-included.md#PureBasic)
* [66 Python](random-number-generator-included.md#Python)
* [67 R](random-number-generator-included.md#R)
* [68 Racket](random-number-generator-included.md#Racket)
* [69 Rascal](random-number-generator-included.md#Rascal)
* [70 REXX](random-number-generator-included.md#REXX)
* [71 Ring](random-number-generator-included.md#Ring)
* [72 Ruby](random-number-generator-included.md#Ruby)
* [73 Run BASIC](random-number-generator-included.md#Run\_BASIC)
* [74 Rust](random-number-generator-included.md#Rust)
* [75 Scala](random-number-generator-included.md#Scala)
* [76 Seed7](random-number-generator-included.md#Seed7)
* [77 Sidef](random-number-generator-included.md#Sidef)
* [78 Sparkling](random-number-generator-included.md#Sparkling)
* [79 Stata](random-number-generator-included.md#Stata)
* [80 Tcl](random-number-generator-included.md#Tcl)
* [81 TI-83 BASIC](random-number-generator-included.md#TI-83\_BASIC)
* [82 TXR](random-number-generator-included.md#TXR)
* [83 UNIX Shell](random-number-generator-included.md#UNIX\_Shell)
* [84 Ursa](random-number-generator-included.md#Ursa)
* [85 Ursala](random-number-generator-included.md#Ursala)
* [86 XPL0](random-number-generator-included.md#XPL0)
* [87 zkl](random-number-generator-included.md#zkl)
* [88 ZX Spectrum Basic](random-number-generator-included.md#ZX\_Spectrum\_Basic)

## [8th](https://rosettacode.org/wiki/Category:8th)

The default random number generator in 8th is a cryptographically strong one using [Fortuna](https://en.wikipedia.org/wiki/Fortuna\_\(PRNG\)), which is seeded from the system's entropy provider. An additional random generator (which is considerably faster) is a [PCG](http://www.pcg-random.org/), though it is not cryptographically strong.

## [ActionScript](https://rosettacode.org/wiki/Category:ActionScript)

In both Actionscript 2 and 3, the type of pseudorandom number generator is implementation-defined. This number generator is accessed through the Math.random() function, which returns a double greater than or equal to 0 and less than 1.[\[1\]](http://livedocs.adobe.com/flash/9.0/ActionScriptLangRefV3/Math.html#random%28%29)[\[2\]](http://flash-reference.icod.de/Math.html#random%28%29) In Actionscript 2, the global random() function returns an integer greater than or equal to 0 and less than the given argument, but it is deprecated and not recommended.[\[3\]](http://flash-reference.icod.de/global\_functions.html#random\(\))

## [Ada](https://rosettacode.org/wiki/Category:Ada)

The Ada standard defines Random Number Generation in Annex A.5.2. There are two kinds of RNGs, Ada.Numerics.Float\_Random for floating point values from 0.0 to 1.0, and Ada.Numerics.Discrete\_Random for pseudo-random values of enumeration types (including integer types). It provides facilities to initialize the generator and to save it's state.

The standard requires the implementation to uniformly distribute over the range of the result type.

The used algorithm is implementation defined. The standard says: "To enable the user to determine the suitability of the random number generators for the intended application, the implementation shall describe the algorithm used and shall give its period, if known exactly, or a lower bound on the period, if the exact period is unknown."

* [Ada 95 RM - A.5.2 Random Number Generation](http://www.adahome.com/rm95/rm9x-A-05-02.html)
* [Ada 2005 RM - A.5.2 Random Number Generation](http://www.adaic.com/standards/05rm/html/RM-A-5-2.html)
* [Ada 2005 RM - A.5.2 Random Number Generation](http://www.adaic.org/resources/add\_content/standards/12rm/html/RM-A-5-2.html)

## [ALGOL 68](https://rosettacode.org/wiki/Category:ALGOL\_68)

Details of the random number generator are in the Revised Reports sections: 10.2.1. and 10.5.1.

* [10.2. The standard prelude - 10.2.1. Environment enquiries](http://vestein.arb-phys.uni-dortmund.de/\~wb/RR/rrA2.html)
* [10.5. The particular preludes and postlude - 10.5.1. The particular preludes](http://vestein.arb-phys.uni-dortmund.de/\~wb/RR/rrA5.html)

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

Note the suitable "next random number" is suggested to be: ( a := ¢ the next pseudo-random ℒ integral value after 'a' from a uniformly distributed sequence on the interval \[ℒ 0,ℒ maxint] ¢; ¢ the real value corresponding to 'a' according to some mapping of integral values \[ℒ 0, ℒ max int] into real values \[ℒ 0, ℒ 1) i.e., such that -0 <= x < 1 such that the sequence of real values so produced preserves the properties of pseudo-randomness and uniform distribution of the sequence of integral values ¢);

Algol68 supports random number generation for all precisions available for the specific implementation. The prefix **ℒ real** indicates all the available precisions. eg **short short real**, **short real**, **real**, **long real**, **long long real** etc

For an ASCII implementation and for **long real** precision these routines would appears as:

```bash
PROC long next random = (REF LONG INT a)LONG REAL: # some suitable next random number #;
INT long last random := # some initial random number #;
PROC long random = LONG REAL: long next random(long last random);
```

## [AutoHotkey](https://rosettacode.org/wiki/Category:AutoHotkey)

The built-in command [Random](http://www.autohotkey.com/docs/commands/Random.htm) generates a pseudo-random number using Mersenne Twister "MT19937" (see documentation).

## [AWK](https://rosettacode.org/wiki/Category:AWK)

The built-in command "rand" generates a pseudo-random uniform distributed random variable. More information is available from the documentation of [gawk](https://www.gnu.org/software/gawk/manual/html\_node/Numeric-Functions.html).

It is important that the RNG is seeded with the funtions "srand", otherwise, the same random number is produced.

Example usage: see [#UNIX\_Shell](https://rosettacode.org/wiki/Random\_number\_generator\_\(included\)#UNIX\_Shell)

## [BASIC](https://rosettacode.org/wiki/Category:BASIC)

The RND function generates a pseudo random number greater than or equal to zero, but less than one. The implementation is machine specific based on contents of the ROM and there is no fixed algorithm.

## [Batch File](https://rosettacode.org/wiki/Category:Batch\_File)

Windows batch files can use the `%RANDOM%` pseudo-variable which returns a pseudo-random number between 0 and 32767. Behind the scenes this is just a call to the C runtime's `rand()` function which uses an LCG in this case:

![equation](https://latex.codecogs.com/gif.latex?X\_%7Bn+1%7D%3DX\_%7Bn%7D\*214013+2531011\*%28mod\*2%5E%7B15%7D%29)

## [BBC BASIC](https://rosettacode.org/wiki/Category:BBC\_BASIC)

The RND function uses a 33-bit maximal-length Linear Feedback Shift Register (LFSR), with 32-bits being used to provide the result. Hence the sequence length is 2^33-1, during which the value zero is returned once and all non-zero 32-bit values are each returned twice.

## [Befunge](https://rosettacode.org/wiki/Category:Befunge)

The ? instruction usually uses the random number generator in the interpreter's language. The original interpreter is written in C and uses rand().

## [C](https://rosettacode.org/wiki/Category:C)

Standard C has rand(). Some implementations of C have other sources of random numbers, along with rand().

### C rand()

The C standard specifies the interface to the rand() and srand() functions in \<stdlib.h>.

* `void srand(unsigned int seed)` begins a new sequence of pseudorandom integers.
* `int rand(void)` returns a pseudorandom integer in the range from 0 to RAND\_MAX.
  * RAND\_MAX must be at least 32767.

The same seed to srand() reproduces the same sequence. The default seed is 1, when a program calls rand() without calling srand(); so srand(1) reproduces the default sequence. ([n1124.pdf](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1124.pdf))

There are no requirements as to the algorithm to be used for generating the random numbers. All versions of rand() return integers that are uniformly distributed in the interval from 0 to RAND\_MAX, but some algorithms have problems in their randomness. For example, the cycle might be too short, or the probabilities might not be independent.

Many popular C libraries implement rand() with a [linear congruential generator](../wiki/Linear\_congruential\_generator/). The specific multiplier and constant varies by implementation, as does which subset of bits within the result is returned as the random number. These rand() functions should not be used where a good quality random number generator is required.

#### BSD rand()

Among current systems, [BSD](https://rosettacode.org/wiki/BSD) might have the worst algorithm for rand(). BSD rand() sets RAND\_MAX to and uses this linear congruential formula:

![formula](https://latex.codecogs.com/gif.latex?state\_%7Bn+1%7D%3D1103515245\*state\_%7Bn%7D+12345\*%28mod2%5E%7B31%7D%29)

![formula2](https://latex.codecogs.com/gif.latex?rand\_%7Bn%7D%3Dstate\_%7Bn%7D)

[FreeBSD](https://github.com/rosettacode.org/mw/index.php?title=FreeBSD\&action=edit\&redlink=1) switched to a different formula, but [NetBSD](https://rosettacode.org/mw/index.php?title=NetBSD\&action=edit\&redlink=1) and [OpenBSD](https://rosettacode.org/wiki/OpenBSD) stayed with this formula. ([NetBSD rand.c](http://cvsweb.netbsd.org/bsdweb.cgi/src/lib/libc/stdlib/rand.c?only\_with\_tag=MAIN), [OpenBSD rand.c](https://www.openbsd.org/cgi-bin/cvsweb/src/lib/libc/stdlib/rand.c))

BSD rand() produces a cycling sequence of only becomes obvious if one uses the low bit to flip a coin.

```
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

* At even seconds: heads, tails, heads, tails, heads, tails, heads, tails, heads, tails.
* At odd seconds: tails, heads, tails, heads, tails, heads, tails, heads, tails, heads.

The low bit manages a uniform distribution between heads and tails, but it has a period length of only 2: it can only flip a coin 2 times before it must repeat itself. Therefore it must alternate heads and tails. This is not a real coin, and these are not truly random flips.

In general, the low bits from BSD rand() are much less random than the high bits. This defect of BSD rand() is so famous that some programs ignore the low bits from rand().

#### Microsoft rand()\[[edit](../mw/index.php)]

Microsoft sets RAND\_MAX to 32767 and uses this linear congruential formula: ] POSIX adds the drand48() family to \<stdlib.h>.

* `void srand48(long seed)` begins a new sequence.
* `double drand48(void)` returns a random double in \[0.0, 1.0).
* `long lrand48(void)` returns a random long in \[0, 2\*\*31).
* `long mrand48(void)` returns a random long in \[-2**31, 2**31).

This family uses a 48-bit linear congruential generator with this formula:

## [C++](https://rosettacode.org/wiki/Category:C%2B%2B)

As part of the C++11 specification the language now includes various forms of random number generation.

While the default engine is implementation specific (ex, unspecified), the following Pseudo-random generators are available in the standard:

* Linear congruential (minstd\_rand0, mitd\_rand)
* Mersenne twister (mt19937, mt19937\_64)
* Subtract with carry (ranlux24\_base, raux48\_base)
* Discard block (ranlux24, ranlux48)
* Shuffle order (knuth\_b)

Additionally, the following distributions are supported:

* Uniform distributions: uniform\_int\_distribution, uniform\_real\_distribution
* Bernoulli distributions: bernoulli\_distribution, geometric\_distribution, binomial\_distribution, negative\_binomial\_distribution
* Poisson distributions: poisson\_distribution, gamma\_distribution, exponential\_distribution, weibull\_distribution, extreme\_value\_distribution
* Normal distributions: normal\_distribution, fisher\_f\_distribution, cauchy\_distribution, lognormal\_distribution, chi\_squared\_distribution, student\_t\_distribution
* Sampling distributions: discrete\_distribution, piecewise\_linear\_distribution, piecewise\_constant\_distribution

Example of use:

**Works with**: [C++11](../wiki/C++11/)

```
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

## [C#](https://rosettacode.org/wiki/Category:C\_sharp)

The .NET Random class says that it uses Knuth's subtractive random number generator algorithm.[\[4\]](https://msdn.microsoft.com/en-us/library/system.random.aspx#remarksToggle)

## [Clojure](https://rosettacode.org/wiki/Category:Clojure)

See Java.

## [CMake](https://rosettacode.org/wiki/Category:CMake)

CMake has a random _string_ generator.

```bash
# Show random integer from 0 to 9999.
[string](https://www.cmake.org/cmake/help/cmake2.6docs.html#command:string)(RANDOM LENGTH 4 ALPHABET 0123456789 number)
[math](https://www.cmake.org/cmake/help/cmake2.6docs.html#command:math)(EXPR number "${number} + 0")  # Remove extra leading 0s.
[message](https://www.cmake.org/cmake/help/cmake2.6docs.html#command:message)(STATUS ${number})
```

The current implementation (in [cmStringCommand.cxx](https://cmake.org/gitweb?p=cmake.git;a=blob;f=Source/cmStringCommand.cxx;hb=HEAD) and [cmSystemTools.cxx](https://cmake.org/gitweb?p=cmake.git;a=blob;f=Source/cmSystemTools.cxx;hb=HEAD)) calls [rand() and srand() from C](../wiki/Random\_number\_generator\_\(included\)/#C). It picks random letters from the alphabet. The probability of each letter is near _1 ÷ length_, but the implementation uses floating-point arithmetic to map _RAND\_MAX + 1_ values onto _length_ letters, so there is a small modulo bias when _RAND\_MAX + 1_ is not a multiple of _length_.

CMake 2.6.x has [bug #9851](http://public.kitware.com/Bug/view.php?id=9851); two random strings might be equal because they use the same seed. CMake 2.8.0 fixes this bug by seeding the random generator only once, during the first call to `string(RANDOM ...)`.

CMake 2.8.5 tries a [secure seed](../wiki/Random\_number\_generator\_\(device\)/) (CryptGenRandom or /dev/urandom) or falls back to high-resolution [system time](../wiki/System\_time/). Older versions seed the random generator with `time(NULL)`, the current time in seconds.

## [Common Lisp](https://rosettacode.org/wiki/Category:Common\_Lisp)

The easiest way to generate random numbers in Common Lisp is to use the built-in rand function after seeding the random number generator. For example, the first line seeds the random number generator and the second line generates a number from 0 to 9

```bash
(setf *random-state* (make-random-state t))
(rand 10)
```

[Common Lisp: The Language, 2nd Ed.](https://www.cs.cmu.edu/Groups/AI/html/cltl/clm/node133.html) does not specify a specific random number generator algorithm.

## [D](https://rosettacode.org/wiki/Category:D)

From std.random:

The generators feature a number of well-known and well-documented methods of generating random numbers. An overall fast and reliable means to generate random numbers is the Mt19937 generator, which derives its name from "[Mersenne Twister](https://en.wikipedia.org/wiki/Mersenne\_twister) with a period of 2 to the power of 19937". In memory-constrained situations, [linear congruential](https://en.wikipedia.org/wiki/Linear\_congruential\_generator) generators such as MinstdRand0 and MinstdRand might be useful. The standard library provides an alias Random for whichever generator it considers the most fit for the target environment.

## [Déjà Vu](https://rosettacode.org/wiki/Category:D%C3%A9j%C3%A0\_Vu)

The standard implementation, `[vu](/wiki/Vu "Vu")`, uses a Mersenne twister.

```bash
!print random-int # prints a 32-bit random integer
```

## [Delphi](https://rosettacode.org/wiki/Category:Delphi)

According to [Wikipedia](https://en.wikipedia.org/wiki/Linear\_congruential\_generator#Parameters\_in\_common\_use), Delphi uses a Linear Congruential Generator.

Random functions:

```bash
 function Random : Extended;
 function Random ( LimitPlusOne  : Integer ) : Integer;
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

## [DWScript](https://rosettacode.org/wiki/Category:DWScript)

DWScript currently uses a 64bit [XorShift](https://en.wikipedia.org/wiki/Xorshift) PRNG, which is a fast and light form of GFSR.

## [EchoLisp](https://rosettacode.org/wiki/Category:EchoLisp)

EchoLisp uses an ARC4 (or RCA4) implementation by David Bau, which replaces the JavaScript Math.random(). Thanks to him. [\[5\]](https://github.com/davidbau/seedrandom). Some examples :

```bash
(random-seed "albert")
(random) → 0.9672510261922906 ; random float in [0 ... 1[
(random 1000)  → 726  ; random integer in [0 ... 1000 [
(random -1000) → -936 ; random integer in ]-1000 1000[

(lib 'bigint)
(random 1e200) → 48635656441292641677...3917639734865662239925...9490799697903133046309616766848265781368
```

## [Elena](https://rosettacode.org/wiki/Category:Elena)

ELENA 4.x :

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

## [Elixir](https://rosettacode.org/wiki/Category:Elixir)

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

## [Erlang](https://rosettacode.org/wiki/Category:Erlang)

Random number generator. The method is attributed to B.A. Wichmann and I.D.Hill, in 'An efficient and portable pseudo-random number generator', Journal of Applied Statistics. AS183. 1982. Also Byte March 1987.

The current algorithm is a modification of the version attributed to Richard A O'Keefe in the standard Prolog library.

Every time a random number is requested, a state is used to calculate it, and a new state produced. The state can either be implicit (kept in the process dictionary) or be an explicit argument and return value. In this implementation, the state (the type ran()) consists of a tuple of three integers.

It should be noted that this random number generator is not cryptographically strong. If a strong cryptographic random number generator is needed for example crypto:rand\_bytes/1 could be used instead.

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

## [Euler Math Toolbox](https://rosettacode.org/wiki/Category:Euler\_Math\_Toolbox)

Bays and Durham as describend in Knuth's book.

## [Factor](https://rosettacode.org/wiki/Category:Factor)

The default RNG used when the `random` vocabulary is used, is the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne\_twister) algorithm [\[6\]](http://docs.factorcode.org/content/article-random.html). But there are other RNGs available, including [SFMT](https://en.wikipedia.org/wiki/SFMT), the system RNG ([/dev/random](https://en.wikipedia.org/wiki/dev/random) on Unix) and [Blum Blum Shub](https://en.wikipedia.org/wiki/Blum\_Blum\_Shub). It's also very easy to implement your own RNG and integrate it into the system. [\[7\]](http://docs.factorcode.org/content/article-random-protocol.html)

## [Fortran](https://rosettacode.org/wiki/Category:Fortran)

Fortran has intrinsic random\_seed() and random\_number() subroutines. Used algorithm of the pseudorandom number generator is compiler dependent (not specified in ISO Fortran Standard, see ISO/IEC 1539-1:2010 (E), 13.7.135 RANDOM NUMBER). For algorithm in GNU gfortran see [https://gcc.gnu.org/onlinedocs/gfortran/RANDOM\_005fNUMBER.html](https://gcc.gnu.org/onlinedocs/gfortran/RANDOM\_005fNUMBER.html) Note that with the GNU gfortran compiler program needs to call random\_seed with a random PUT= argument to get a pseudorandom number otherwise the sequence always starts with the same number. Intel compiler ifort reinitializes the seed randomly without PUT argument to random value using the system date and time. Here we are seeding random\_seed() with some number obtained from the Linux urandom device.

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

## [FreeBASIC](https://rosettacode.org/wiki/Category:FreeBASIC)

FreeBASIC has a Rnd() function which produces a pseudo-random double precision floating point number in the half-closed interval \[0, 1) which can then be easily used to generate pseudo-random numbers (integral or decimal) within any range.

The sequence of pseudo-random numbers can either by seeded by a parameter to the Rnd function itself or to the Randomize statement and, if omitted, uses a seed based on the system timer.

However, a second parameter to the Randomize statement determines which of 5 different algorithms is used to generate the pseudo-random numbers:

1\. Uses the C runtime library's rand() function (based on LCG) which differs depending on the platform but produces a low degree of randomness.

2\. Uses a fast, platform independent, algorithm with 32 bit granularity and a reasonable degree of randomness. The basis of this algorithm is not specified in the language documentation.

3\. Uses the Mersenne Twister algorithm (based on GFSR) which is platform independent, with 32 bit granularity and a high degree of randomness. This is good enough for most non-cryptographic purposes.

4\. Uses a QBASIC compatible algorithm which is platform independent, with 24 bit granularity and a low degree of randomness.

5\. Uses system features (Win32 Crypto API or /dev/urandom device on Linux) to generate pseudo-random numbers, with 32 bit granularity and a very high degree of randomness (cryptographic strength).

A parameter of 0 can also be used (and is the default if omitted) which uses algorithm 3 in the -lang fb dialect, 4 in the -lang qb dialect and 1 in the -lang fblite dialect.

## [Free Pascal](https://rosettacode.org/wiki/Category:Free\_Pascal)

FreePascal's function random uses the MersenneTwister (for further details, see the file rtl/inc/system.inc). The random is conform MT19937 and is therefor compatible with e.g. the C++11 MT19937 implementation.

## [FutureBasic](https://rosettacode.org/wiki/Category:FutureBasic)

Syntax:

```bash
randomInteger = rnd(expr)
```

This function returns a pseudo-random long integer uniformly distributed in the range 1 through expr. The expr parameter should be greater than 1, and must not exceed 65536. If the value returned is to be assigned to a 16-bit integer (randomInteger), expr should not exceed 32767. The actual sequence of numbers returned by rnd depends on the random number generator's "seed" value. (Note that rnd(1) always returns the value 1.)

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

## [GAP](https://rosettacode.org/wiki/Category:GAP)

GAP may use two algorithms : MersenneTwister, or algorithm A in section 3.2.2 of TAOCP (which is the default). One may create several _random sources_ in parallel, or a global one (based on the TAOCP algorithm).

```bash
# Creating a random source
rs := RandomSource(IsMersenneTwister);

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

# Random element of Z/23Z :
Random(Integers mod 23);
```

## [Go](https://rosettacode.org/wiki/Category:Go)

Go has two random number packages in the standard library and another package in the "subrepository."

1. [math/rand](https://golang.org/pkg/math/rand/) in the standard library provides general purpose random number support, implementing some sort of feedback shift register. (It uses a large array commented "feeback register" and has variables named "tap" and "feed.") Comments in the code attribute the algorithm to DP Mitchell and JA Reeds. A little more insight is in [this issue](https://github.com/golang/go/issues/21835) in the Go issue tracker.
2. [crypto/rand](https://golang.org/pkg/crypto/rand/), also in the standard library, says it "implements a cryptographically secure pseudorandom number generator." I think though it should say that it _accesses_ a cryptographically secure pseudorandom number generator. It uses `/dev/urandom` on Unix-like systems and the CryptGenRandom API on Windows.
3. [x/exp/rand](https://godoc.org/golang.org/x/exp/rand) implements the Permuted Congruential Generator which is also described in the issue linked above.

## [Golfscript](https://rosettacode.org/wiki/Category:Golfscript)

Golfscript uses Ruby's Mersenne Twister algorithm

`~rand` produces a random integer between 0 and n-1, where n is a positive integer piped into the program

## [Groovy](https://rosettacode.org/wiki/Category:Groovy)

Same as Java.

## [Haskell](https://rosettacode.org/wiki/Category:Haskell)

The [Haskell 98 report](https://www.haskell.org/onlinereport/random.html) specifies an interface for pseudorandom number generation and requires that implementations be minimally statistically robust. It is silent, however, on the choice of algorithm.

## [Icon](https://rosettacode.org/wiki/Category:Icon) and [Unicon](https://rosettacode.org/wiki/Category:Unicon)

Icon and Unicon both use the same linear congruential random number generator x := (x \* 1103515245 + 453816694) mod 2^31. Icon uses an initial seed value of 0 and Unicon randomizes the initial seed.

This LCRNG has a number of well documented quirks (see [The Icon Analyst issues #26, 28, 38](https://www.cs.arizona.edu/icon/analyst/ia.htm)) relating to the choices of an even additive and a power of two modulus. This LCRNG produces two independent sequences of length 2^30 one of even numbers the other odd.

Additionally, the**Library:** [Icon Programming Library](../wiki/Category:Icon\_Programming\_Library/)[random](https://www.cs.arizona.edu/icon/library/src/procs/random.icn) provides related procedures including a parametrized LCRNG that defaults to the built-in values.

## [Io](https://rosettacode.org/wiki/Category:Io)

Io's [Random object](http://iolanguage.org/scm/io/docs/reference/index.html#/Math/Random/Random) uses the Mersenne Twister algorithm.

## [Inform 7](https://rosettacode.org/wiki/Category:Inform\_7)

Inform's random functions are built on the random number generator exposed at runtime by the virtual machine, which is implementation-defined.

## [J](https://rosettacode.org/wiki/Category:J)

By default J's `?` primitive (Roll/Deal) uses the Mersenne twister algorithm, but can be set to use a number of other algorithms as detailed on the [J Dictionary page for Roll/Deal](http://www.jsoftware.com/help/dictionary/d640.htm).

## [Java](https://rosettacode.org/wiki/Category:Java)

Java's `Random` class uses a [Linear congruential formula](https://en.wikipedia.org/wiki/Linear\_congruential\_generator), as described in [its documentation](http://java.sun.com/javase/6/docs/api/java/util/Random.html). The commonly used `Math.random()` uses a `Random` object under the hood.

## [JavaScript](https://rosettacode.org/wiki/Category:JavaScript)

The only built-in random number generation facility is `Math.random()`, which returns a floating-point number greater than or equal to 0 and less than 1, with approximately uniform distribution. The standard (ECMA-262) does not specify what algorithm is to be used.

## [Julia](https://rosettacode.org/wiki/Category:Julia)

Julia's [built-in random-number generation functions](http://docs.julialang.org/en/latest/stdlib/base/#random-numbers), `rand()` etcetera, use the Mersenne Twister algorithm.

## [Kotlin](https://rosettacode.org/wiki/Category:Kotlin)

As mentioned in the Java entry, the java.util.Random class uses a linear congruential formula and is not therefore cryptographically secure. However, there is also a derived class, java.security.SecureRandom, which can be used for cryptographic purposes

## [Lua](https://rosettacode.org/wiki/Category:Lua)

Lua's `math.random()` is an interface to the C `rand()` function provided by the OS libc; its implementation varies by platform.

## [Mathematica](https://rosettacode.org/wiki/Category:Mathematica)

Mathematica 7, by default, uses an Extended Cellular Automaton method ("ExtendedCA") to generate random numbers. The main PRNG functions are `RandomReal[]` and `RandomInteger[]` You can specify alternative generation methods including the Mersenne Twister and a Linear Congruential Generator (the default earlier versions). Information about random number generation is provided at [Mathematica](https://reference.wolfram.com/mathematica/tutorial/RandomNumberGeneration.html#185956823).

## [MATLAB](https://rosettacode.org/wiki/Category:MATLAB)

MATLAB uses the Mersenne Twister as its default random number generator. Information about how the "rand()" function is utilized is given at [MathWorks](https://www.mathworks.com/help/techdoc/ref/rand.html).

## [Maxima](https://rosettacode.org/wiki/Category:Maxima)

Maxima uses a Lisp implementation of the Mersenne Twister. See `? random` for help, or file `share/maxima/5.28.0-2/src/rand-mt19937.lisp` for the source code.

There are also random generators for several [distributions](https://en.wikipedia.org/wiki/Probability\_distribution) in package `distrib` :

* `[random_bernoulli](https://en.wikipedia.org/wiki/Bernoulli_distribution "wp:Bernoulli distribution")`
* `[random_beta](https://en.wikipedia.org/wiki/Beta_distribution "wp:Beta distribution")`
* `[random_binomial](https://en.wikipedia.org/wiki/Binomial_distribution "wp:Binomial distribution")`
* `[random_cauchy](https://en.wikipedia.org/wiki/Cauchy_distribution "wp:Cauchy distribution")`
* `[random_chi2](https://en.wikipedia.org/wiki/Chi-squared_distribution "wp:Chi-squared distribution")`
* `[random_continuous_uniform](https://en.wikipedia.org/wiki/Uniform_distribution_(continuous) "wp:Uniform distribution (continuous)")`
* `[random_discrete_uniform](https://en.wikipedia.org/wiki/Uniform_distribution_(discrete) "wp:Uniform distribution (discrete)")`
* `[random_exp](https://en.wikipedia.org/wiki/Exponential_distribution "wp:Exponential distribution")`
* `[random_f](https://en.wikipedia.org/wiki/F-distribution "wp:F-distribution")`
* `[random_gamma](https://en.wikipedia.org/wiki/Gamma_distribution "wp:Gamma distribution")`
* `[random_general_finite_discrete](https://en.wikipedia.org/wiki/Categorical_distribution "wp:Categorical distribution")`
* `[random_geometric](https://en.wikipedia.org/wiki/Geometric_distribution "wp:Geometric distribution")`
* `[random_gumbel](https://en.wikipedia.org/wiki/Gumbel_distribution "wp:Gumbel distribution")`
* `[random_hypergeometric](https://en.wikipedia.org/wiki/Hypergeometric_distribution "wp:Hypergeometric distribution")`
* `[random_laplace](https://en.wikipedia.org/wiki/Laplace_distribution "wp:Laplace distribution")`
* `[random_logistic](https://en.wikipedia.org/wiki/Logistic_distribution "wp:Logistic distribution")`
* `[random_lognormal](https://en.wikipedia.org/wiki/Lognormal_distribution "wp:Lognormal distribution")`
* `[random_negative_binomial](https://en.wikipedia.org/wiki/Negative_binomial_distribution "wp:Negative binomial distribution")`
* `[random_noncentral_chi2](https://en.wikipedia.org/wiki/Noncentral_chi-squared_distribution "wp:Noncentral chi-squared distribution")`
* `[random_noncentral_student_t](https://en.wikipedia.org/wiki/Noncentral_t-distribution "wp:Noncentral t-distribution")`
* `[random_normal](https://en.wikipedia.org/wiki/Normal_distribution "wp:Normal distribution")`
* `[random_pareto](https://en.wikipedia.org/wiki/Pareto_distribution "wp:Pareto distribution")`
* `[random_poisson](https://en.wikipedia.org/wiki/Poisson_distribution "wp:Poisson distribution")`
* `[random_rayleigh](https://en.wikipedia.org/wiki/Rayleigh_distribution "wp:Rayleigh distribution")`
* `[random_student_t](https://en.wikipedia.org/wiki/Student%27s_t-distribution "wp:Student's t-distribution")`
* `[random_weibull](https://en.wikipedia.org/wiki/Weibull_distribution "wp:Weibull distribution")`

Note: the package `distrib` also has functions starting with `pdf`, `cdf`, `quantile`, `mean`, `var`, `std`, `skewness` or `kurtosis` instead of `random`, except the Cauchy distribution, which does not have [moments](https://en.wikipedia.org/wiki/Moment\_\(mathematics\)).

## [Modula-3](https://rosettacode.org/wiki/Category:Modula-3)

The Random interface in Modula-3 states that it uses "an additive generator based on Knuth's Algorithm 3.2.2A".

## [Nemerle](https://rosettacode.org/wiki/Category:Nemerle)

Uses .Net Random class; so, as mentioned under C#, above, implements Knuth's subtractive random number generator algorithm. Random class documentation at [MSDN](https://msdn.microsoft.com/en-us/library/system.random.aspx#remarksToggle).

## [NetRexx](https://rosettacode.org/wiki/Category:NetRexx)

As NetRexx runs in the JVM it simply leverages the Java library. See [Java](random-number-generator-included.md#Java) for details of the algorithms used.

## [Nim](https://rosettacode.org/wiki/Category:Nim)

There are two PRNGs provided in the standard library:

* **random** : Based on xoroshiro128+ (xor/rotate/shift/rotate), see [here](http://xoroshiro.di.unimi.it/).
* **mersenne** : The Mersenne Twister.

## [OCaml](https://rosettacode.org/wiki/Category:OCaml)

OCaml provides a module called [Random](http://caml.inria.fr/pub/docs/manual-ocaml/libref/Random.html) in its standard library. It used to be a "Linear feedback shift register" pseudo-random number generator (References: Robert Sedgewick, "Algorithms", Addison-Wesley). It is now (as of version 3.12.0) a "lagged-Fibonacci F(55, 24, +) with a modified addition function to enhance the mixing of bits." It passes the Diehard test suite.

## [Octave](https://rosettacode.org/wiki/Category:Octave)

As explained [here](https://www.gnu.org/software/octave/doc/interpreter/Special-Utility-Matrices.html#Special-Utility-Matrices) (see **rand** function), Octave uses the "Mersenne Twister with a period of 2^19937-1".

## [Oz](https://rosettacode.org/wiki/Category:Oz)

Oz provides a binding to the C `[rand](https://www.opengroup.org/onlinepubs/000095399/functions/rand.html)` function as `[OS.rand](http://www.mozart-oz.org/home/doc/system/node56.html#label719)`.

## [PARI/GP](https://rosettacode.org/wiki/Category:PARI/GP)

`random` uses Richard Brent's [xorgens](http://wwwmaths.anu.edu.au/\~brent/random.html). It's a member of the xorshift class of PRNGs and provides good, fast pseudorandomness (passing the BigCrush test, unlike the Mersenne twister), but it is not cryptographically strong. As implemented in PARI, its period is "at least.

```bash
setrand(3)
random(6)+1
\\ chosen by fair dice roll.
\\ guaranteed to the random.
```

## [Pascal](https://rosettacode.org/wiki/Category:Pascal)

See <#Delphi> and [#Free Pascal](random-number-generator-included.md#Free\_Pascal).

Random functions:

```bash
 function  Random(l: LongInt) : LongInt;
 function  Random : Real;
 procedure Randomize;
```

## [Perl](https://rosettacode.org/wiki/Category:Perl)

Previous to Perl 5.20.0 (May 2014), Perl's `[rand](https://perldoc.perl.org/functions/rand.html)` function will try and call `[drand48](https://www.opengroup.org/onlinepubs/007908775/xsh/drand48.html)`, `[random](https://www.opengroup.org/onlinepubs/000095399/functions/random.html)` or `[rand](https://www.opengroup.org/onlinepubs/000095399/functions/rand.html)` from the C library `[stdlib.h](https://www.opengroup.org/onlinepubs/000095399/basedefs/stdlib.h.html)` in that order.

Beginning with Perl 5.20.0, a drand48() implementation is built into Perl and used on all platforms. The implementation is from FreeBSD and uses a 48-bit linear congruential generator with this formula:

Seeds for drand48 are 32-bit and the initial seed uses 4 bytes of data read from /dev/urandom if possible; a 32-bit mix of various system values otherwise.

Additionally, there are many PRNG's available as modules. Two good Mersenne Twister modules are [Math::Random::MTwist](https://metacpan.org/pod/Math::Random::MTwist) and [Math::Random::MT::Auto](https://metacpan.org/pod/Math::Random::MT::Auto). Modules supporting other distributions can be found in [Math::Random](https://metacpan.org/pod/Math::Random) and [Math::GSL::Randist](https://metacpan.org/pod/Math::GSL::Randist) among others. CSPRNGs include [Bytes::Random::Secure](https://metacpan.org/pod/Bytes::Random::Secure), [Math::Random::Secure](https://metacpan.org/pod/Math::Random::Secure), [Math::Random::ISAAC](https://metacpan.org/pod/Math::Random::ISAAC), and many more.

## [Perl 6](https://rosettacode.org/wiki/Category:Perl\_6)

The implementation underlying the `rand` function is platform and VM dependent. The JVM backend uses that platform's SecureRandom class.

## [Phix](https://rosettacode.org/wiki/Category:Phix)

The rand(n) routine returns an integer in the range 1 to n, and rnd() returns a floating point number between 0.0 and 1.0. In both cases the underlying algorithm is just about as trivial as it can be, certainly not suitable for serious cryptographic work. There are at least a couple of Mersenne twister components in the archive.

## [PHP](https://rosettacode.org/wiki/Category:PHP)

PHP has two random number generators: `[rand](http://us3.php.net/manual/en/function.rand.php)`, which uses the underlying C library's `rand` function; and `[mt_rand](http://us3.php.net/manual/en/function.mt-rand.php)`, which uses the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne\_twister) algorithm.

## [PicoLisp](https://rosettacode.org/wiki/Category:PicoLisp)

PicoLisp uses a linear congruential generator in the built-in (rand) function, with a multiplier suggested in Knuth's "Seminumerical Algorithms". See the [documentation](http://software-lab.de/doc/refR.html#rand).

## [PL/I](https://rosettacode.org/wiki/Category:PL/I)

Values produced by IBM Visualage PL/I compiler built-in random number generator are uniformly distributed between 0 and 1 \[0 <= random < 1]

It uses a multiplicative congruential method:

```bash
seed(x) = mod(950706376 * seed(x-1), 2147483647)
random(x) = seed(x) / 2147483647
```

## [PL/SQL](https://rosettacode.org/wiki/Category:PL/SQL)

Oracle Database has two packages that can be used for random numbers generation.

### DBMS\_RANDOM

The DBMS\_RANDOM package provides a built-in random number generator. This package is not intended for cryptography. It will automatically initialize with the date, user ID, and process ID if no explicit initialization is performed. If this package is seeded twice with the same seed, then accessed in the same way, it will produce the same results in both cases.

```bash
DBMS_RANDOM.RANDOM --produces integers in [-2^^31, 2^^31).
DBMS_RANDOM.VALUE  --produces numbers in [0,1) with 38 digits of precision.
DBMS_RANDOM.NORMAL --produces normal distributed numbers with a mean of 0 and a variance of 1
```

### DBMS\_CRYPTO

The DBMS\_CRYPTO package contains basic cryptographic functions and procedures. The DBMS\_CRYPTO.RANDOMBYTES function returns a RAW value containing a cryptographically secure pseudo-random sequence of bytes, which can be used to generate random material for encryption keys. This function is based on the RSA X9.31 PRNG (Pseudo-Random Number Generator).

```bash
DBMS_CRYPTO.RANDOMBYTES --returns RAW value
DBMS_CRYPTO.RANDOMINTEGER --produces integers in the BINARY_INTEGER datatype
DBMS_CRYPTO.RANDOMNUMBER --produces integer in the NUMBER datatype in the range of [0..2**128-1]
```

## [PowerShell](https://rosettacode.org/wiki/Category:PowerShell)

The [`Get-Random`](https://technet.microsoft.com/en-us/library/dd315402.aspx) cmdlet (part of PowerShell 2) uses the .NET-supplied pseudo-random number generator which uses Knuth's subtractive method; see [C#](random-number-generator-included.md#C.23).

## [PureBasic](https://rosettacode.org/wiki/Category:PureBasic)

PureBasic has two random number generators, `Random()` and `CryptRandom()`. `Random()` uses a RANROT type W generator [\[8\]](http://www.agner.org/random/theory/chaosran.pdf). `CryptRandom()` uses a very strong PRNG that makes use of a cryptographic safe random number generator for its 'seed', and refreshes the seed if such data is available. The exact method used for `CryptRandom()` is uncertain.

## [Python](https://rosettacode.org/wiki/Category:Python)

Python uses the [Mersenne twister](https://en.wikipedia.org/wiki/Mersenne\_twister) algorithm accessed via the built-in [random module](https://docs.python.org/library/random.html).

## [R](https://rosettacode.org/wiki/Category:R)

For uniform random numbers, R may use Wichmann-Hill, Marsaglia-multicarry, Super-Duper, Mersenne-Twister, or Knuth-TAOCP (both 1997 and 2002 versions), or a user-defined method. The default is Mersenne Twister.

R is able to generate random numbers from a variety of distributions, e.g.

[READ SOURCE](https://rosettacode.org/wiki/Random\_number\_generator\_\(included\))
