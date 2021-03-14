# bisque - C++ frontend as a library

bisque is a project which cleaves the C++ front end parser from GCC and wraps it up into it's own library to allow it to be consumed from other applications who wish to extract AST information from C++ code.

It is broken into two parts, the first is the core front-end parser itself, which does all the heavy lifting with regards to parsing the input into an internal representation, that is [`bisque-core`](bisque-core). The second part is an LGPL licensed library which wraps bisque-core in a nice and easy to consume API, and also, by virtue of being LGPL licensed, prevents the GPL from slithering out, that is [`libbisque`](libbisque), which is also the primary linking target.


## Licenses

bisque is licensed under 2 individual licenses, the first is the code from GCC, the second is the wrapper library.

The core C++ parser frontend [`bisque-core`](bisque-core) is based on code from GCC and therefore licensed under the GPLv3, the full text of which can be found in [LICENSE.gpl](LICENSE.gpl).

The wrapper library [`libbisque`](libbisque) is licensed under the LGPLv3 or newer, the full text of which can be found in [LICENSE.lgpl](LICENSE.lgpl).
