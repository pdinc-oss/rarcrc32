This is a python written "rar" crc32 utility, it is released under the Apache 2.0 license.

It was written when cksum could not [easily?] produce the same CRC32 used by rar (and ZIP?).

Its behavior mimics cksum, sha\*sum, etc., except it omits the asterisk (\*)

    $ ./rarcrc32sum < rarcrc32sum
    40EF0250
    
    $ ./rarcrc32sum rarcrc32sum
    40EF0250        rarcrc32sum
    
    $ ./rarcrc32sum rarcrc32sum rarcrc32sum
    40EF0250        rarcrc32sum
    40EF0250        rarcrc32sum
    
    $ ./rarcrc32sum rarcrc32sum 404file rarcrc32sum
    40EF0250        rarcrc32sum
    Error:  404file
    40EF0250        rarcrc32sum
    
    $ ./rarcrc32sum rarcrc32sum 404file rarcrc32sum 2> /dev/null
    40EF0250        rarcrc32sum
    40EF0250        rarcrc32sum
