## Haskell Cryptography

The collects together existing Haskell cryptographic functions into one
cabalized package, together with HUnit tests, QuickCheck property tests
and examples. It is a significant change from previous versions and now
only contains cryptographic functions; the functions for dealing with
ASN.1, X.509 certificates and PKCS\#8 will be provided by an entirely
separate library reducing the number of dependencies.

This release contains:

-   DES

-   Blowfish

-   AES

-   TEA

-   Cipher Block Chaining (CBC)

-   PKCS\#5 and nulls padding

-   SHA-1

-   MD5

-   RSA

Haddock documentation for the library is available.

System Requirements
===================

-   The code has been tested on GHC 6.6 and Hugs Version September 2006.
    It does not currently work with YHC because of the lack of
    <span>Data.Word</span> and <span>Data.Bits</span>.

-   It <span>*no longer*</span> requires the use of
    <span>NewBinary.Binary</span>.

Installation Instructions
=========================

Get the sources:

``` bash
darcs get --tag "4.2.0" http://code.haskell.org/crypto
```

Build and install ready for testing:

``` bash
ghc -o Setup Setup.hs -package Cabal
./Setup configure --prefix=/my/chosen/dir
./Setup build
./Setup install --user
```

Run the tests.

``` bash
cd /my/chosen/dir/bin
./RSATest
./SymmetricTest
./QuickTest
```

You can now run the examples to confirm further that everything is
working satisfactorily. When you are happy, build and install them in
their final destination:

``` bash
./Setup unregister --user
./Setup clean
./Setup configure
./Setup build
./Setup install
```

To Do
=====

In no particular order:

-   Incorporate other symmetric key algorithms already coded in Haskell.

-   Performance analysis as Blowfish ought to run more quickly than DES.

-   Other modes / padding schemes.

-   Extend typechecking to ensure that only the appropriate key sizes
    are used for a given algorithm.

-   Improve performance, for example, for SHA1. This runs an order of
    magnitude faster but, with respect to the authors, doesn't feel
    that functional.

-   Get rid of the GPL code.

Contact
=======

All questions, comments, bug reports, flames, requests for updates /
changes and suggestions should be directed to Dominic Steinitz and
logged.

Licensing
=========

The modules in the library come from different authors and have been
released under different licences.

Contributors
------------

### Codec.Binary

<span>|p<span>6cm</span>|p<span>3cm</span>|p<span>3cm</span>|p<span>1cm</span>|</span>
Codec.Binary.BubbleBabble & John Meacham & Copyright &#169; 2008, All rights
reserved & BSD

### Codec.Text

<span>|p<span>6cm</span>|p<span>3cm</span>|p<span>3cm</span>|p<span>1cm</span>|</span>
Codec.Text.Raw & Dominic Steinitz & Copyright &#169; 2006, All rights
reserved & BSD

### Codec.Encryption

<span>|p<span>6cm</span>|p<span>3cm</span>|p<span>3cm</span>|p<span>1cm</span>|</span>
Codec.Encryption.AES & Lukasz Anforowicz & Copyright &#169; 2005, All rights
reserved & BSD
Codec.Encryption.AESAux & Dominic Steinitz & Copyright &#169; 2005, All
rights reserved & BSD
Codec.Encryption.Blowfish & Doug Hoyte & Copyright &#169; 2005, All rights
reserved & BSD
Codec.Encryption.BlowfishAux & Dominic Steinitz & Copyright &#169; 2005, All
rights reserved & BSD
Codec.Encryption.TEA & John Meacham & Copyright &#169; 2008, All rights
reserved & BSD
Codec.Encryption.DES & Ian Lynagh & Copyright &#169; 2005, All rights
reserved & BSD
Codec.Encryption.DESAux & Dominic Steinitz & Copyright &#169; 2005, All
rights reserved & BSD
Codec.Encryption.Modes & Dominic Steinitz & Copyright &#169; 2005, All rights
reserved & BSD
Codec.Encryption.Padding & Dominic Steinitz & Copyright &#169; 2005, All
rights reserved & BSD
Codec.Encryption.RSA & David Sankel & Copyright &#169; 2005, All rights
reserved & GPL
Codec.Encryption.RSA.EMEOAEP & David Sankel & Copyright &#169; 2005, All
rights reserved & GPL
Codec.Encryption.RSA.MGF & Dominic Steinitz & Copyright &#169; 2005, All
rights reserved & BSD
Codec.Encryption.RSA.NumberTheory & David Sankel & Copyright &#169; 2005, All
rights reserved & GPL

### Codec

<span>|p<span>6cm</span>|p<span>3cm</span>|p<span>3cm</span>|p<span>1cm</span>|</span>
Codec.Utils & Dominic Steinitz & Copyright &#169; 2005, All rights reserved &
BSD

### Data.Digest

<span>|p<span>6cm</span>|p<span>3cm</span>|p<span>3cm</span>|p<span>1cm</span>|</span>
Data.Digest.MD5 & Dominic Steinitz & Copyright &#169; 2005, All rights
reserved & BSD
Data.Digest.MD5Aux & Ian Lynagh & Copyright &#169; 2005, All rights reserved
& BSD
Data.Digest.SHA1 & Dominic Steinitz & Copyright &#169; 2005, All rights
reserved & BSD

### Data

<span>|p<span>6cm</span>|p<span>3cm</span>|p<span>3cm</span>|p<span>1cm</span>|</span>
Data.LargeWord & Dominic Steinitz & Copyright &#169; 2005, All rights
reserved & BSD

### Tests and Examples

<span>|p<span>6cm</span>|p<span>3cm</span>|p<span>3cm</span>|p<span>1cm</span>|</span>
RSATest & Dominic Steinitz & Copyright &#169; 2005, All rights reserved &
BSD
QuickTest & Dominic Steinitz & Copyright &#169; 2005, All rights reserved &
BSD
SymmetricTest & Dominic Steinitz & Copyright &#169; 2005, All rights reserved
& BSD

The BSD License
---------------

This license is based on .

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

-   Redistributions of source code must retain the above copyright
    notice, this list of conditions and the following disclaimer.

-   Redistributions in binary form must reproduce the above copyright
    notice, this list of conditions and the following disclaimer in the
    documentation and/or other materials provided with the distribution.

-   The names of its contributors may not be used to endorse or promote
    products derived from this software without specific prior
    written permission.

This software is provided by the copyright holders and contributors "AS
IS" and any express or implied warranties, including, but not limited
to, the implied warranties of merchantability and fitness for a
particular purpose are disclaimed. In no event shall the copyright
onwers or contributors be liable for any direct, indirect, incidental,
special, exemplary, or consequential damages (including, but not limited
to, procurement of substitute goods or services; loss of use, data, or
profits; or business interruption) however caused and on any theory of
liability, whether in contract, strict liability, or tort (including
negligence or otherwise) arising in any way out of the use of this
software, even if advised of the possibility of such damage.

The GNU General Public License (GPL)
------------------------------------

This program is free software; you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the
Free Software Foundation; either version 2 of the License, or (at your
option) any later version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General
Public License for more details.

You can find a copy of the GNU General Public License ; if not, write to
the Free Software Foundation, Inc., 59 Temple Place, Suite 330, Boston,
MA 02111-1307 USA

Disclaimer
==========

Cryptography is a notoriously easy area in which to make mistakes, not
necessarily with the algorithms but with how they are implemented (for
example not protecting keys, using weak keys and so on). For a readable
account of some of the pitfalls, see [Ross Anderson](http://www.cl.cam.ac.uk/users/rja14/)'s book.

This software is provided by the copyright holders and contributors "AS
IS" and any express or implied warranties, including, but not limited
to, the implied warranties of merchantability and fitness for a
particular purpose are disclaimed. In no event shall the copyright
onwers or contributors be liable for any direct, indirect, incidental,
special, exemplary, or consequential damages (including, but not limited
to, procurement of substitute goods or services; loss of use, data, or
profits; or business interruption) however caused and on any theory of
liability, whether in contract, strict liability, or tort (including
negligence or otherwise) arising in any way out of the use of this
software, even if advised of the possibility of such damage.

Acknowledgements
================

- Doug Hoyte (HardCore SoftWare)

- Anatoly Zaretsky

- [Ian Lynagh](http://web.comlab.ox.ac.uk/oucl/work/ian.lynagh)

- [David Sankel](http://www.electronconsulting.com/whois.html)

- [Ross Paterson](http://www.soi.city.ac.uk/~ross)

- Lukasz Anforowicz

- [Warrick Gray](http://homepages.paradise.net.nz/warrickg/haskell/http/)

- [Russell O'Connor](http://r6.ca)

- Spencer Janssen

This document was last updated on 7th December 2008. &#169; 2006-2008 Dominic
Steinitz.
