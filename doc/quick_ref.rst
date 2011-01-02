.. currentmodule:: bitstring

******************
Quick Reference
******************

``class ConstBitArray(object)``
-------------------------------

A ``ConstBitArray`` is the most basic class. It is immutable, so once created its value cannot change. It is a base class for all the other classes in the `bitstring` module.

Methods
^^^^^^^

 *   :meth:`~ConstBitArray.all` -- Check if all specified bits are set to 1 or 0.
 *   :meth:`~ConstBitArray.any` -- Check if any of specified bits are set to 1 or 0.
 *   :meth:`~ConstBitArray.cut` -- Create generator of constant sized chunks.
 *   :meth:`~ConstBitArray.endswith` -- Return whether the bitstring ends with a sub-string.
 *   :meth:`~ConstBitArray.find` -- Find a sub-bitstring in the current bitstring.
 *   :meth:`~ConstBitArray.findall` -- Find all occurences of a sub-bitstring in the current bitstring.
 *   :meth:`~ConstBitArray.join` -- Join bitstrings together using current bitstring.
 *   :meth:`~ConstBitArray.rfind` -- Seek backwards to find a sub-bitstring.
 *   :meth:`~ConstBitArray.split` -- Create generator of chunks split by a delimiter.
 *   :meth:`~ConstBitArray.startswith` -- Return whether the bitstring starts with a sub-bitstring.
 *   :meth:`~ConstBitArray.tobytes` -- Return bitstring as bytes, padding if needed.
 *   :meth:`~ConstBitArray.tofile` -- Write bitstring to file, padding if needed.
 *   :meth:`~ConstBitArray.unpack` -- Interpret bits using format string.

Special methods
^^^^^^^^^^^^^^^

    Also available are the operators ``[]``, ``==``, ``!=``, ``+``, ``*``, ``~``, ``<<``, ``>>``, ``&``, ``|``, ``^``.

Properties
^^^^^^^^^^

 *   :attr:`~ConstBitArray.bin` -- The bitstring as a binary string.
 *   :attr:`~ConstBitArray.bool` -- For single bit bitstrings, interpret as True or False.
 *   :attr:`~ConstBitArray.bytes` -- The bitstring as a bytes object.
 *   :attr:`~ConstBitArray.float` -- Interpret as a floating point number.
 *   :attr:`~ConstBitArray.floatbe` -- Interpret as a big-endian floating point number.
 *   :attr:`~ConstBitArray.floatle` -- Interpret as a little-endian floating point number.
 *   :attr:`~ConstBitArray.floatne` -- Interpret as a native-endian floating point number.
 *   :attr:`~ConstBitArray.hex` -- The bitstring as a hexadecimal string.
 *   :attr:`~ConstBitArray.int` -- Interpret as a two's complement signed integer.
 *   :attr:`~ConstBitArray.intbe` -- Interpret as a big-endian signed integer.
 *   :attr:`~ConstBitArray.intle` -- Interpret as a little-endian signed integer.
 *   :attr:`~ConstBitArray.intne` -- Interpret as a native-endian signed integer.
 *   :attr:`~ConstBitArray.len` -- Length of the bitstring in bits.
 *   :attr:`~ConstBitArray.oct` -- The bitstring as an octal string.
 *   :attr:`~ConstBitArray.se` -- Interpret as a signed exponential-Golomb code.
 *   :attr:`~ConstBitArray.ue` -- Interpret as an unsigned exponential-Golomb code.
 *   :attr:`~ConstBitArray.uint` -- Interpret as a two's complement unsigned integer.
 *   :attr:`~ConstBitArray.uintbe` -- Interpret as a big-endian unsigned integer.
 *   :attr:`~ConstBitArray.uintle` -- Interpret as a little-endian unsigned integer.
 *   :attr:`~ConstBitArray.uintne` -- Interpret as a native-endian unsigned integer.

``class BitArray(ConstBitArray)``
---------------------------------

This class adds mutating methods to `ConstBitArray`.

Additional methods
^^^^^^^^^^^^^^^^^^

 *   :meth:`~BitArray.append` -- Append a bitstring.
 *   :meth:`~BitArray.byteswap` -- Change byte endianness in-place.
 *   :meth:`~BitArray.insert` -- Insert a bitstring.
 *   :meth:`~BitArray.invert` -- Flip bit(s) between one and zero.
 *   :meth:`~BitArray.overwrite` -- Overwrite a section with a new bitstring.
 *   :meth:`~BitArray.prepend` -- Prepend a bitstring.
 *   :meth:`~BitArray.replace` -- Replace occurences of one bitstring with another.
 *   :meth:`~BitArray.reverse` -- Reverse bits in-place.
 *   :meth:`~BitArray.rol` -- Rotate bits to the left.
 *   :meth:`~BitArray.ror` -- Rotate bits to the right.
 *   :meth:`~BitArray.set` -- Set bit(s) to 1 or 0.

Additional special methods
^^^^^^^^^^^^^^^^^^^^^^^^^^

    Mutating operators are available: ``[]``, ``<<=``, ``>>=``, ``*=``, ``&=``, ``|=`` and ``^=``.

Attributes
^^^^^^^^^^

    The same as ``ConstBitArray``, except that they are all writable as well as readable.


``class ConstBitStream(ConstBitArray)``
---------------------------------------

This class, previously known as just ``Bits`` (which is an alias for backward-compatibility), adds a bit position and methods to read and navigate in the bitstream.

Additional methods
^^^^^^^^^^^^^^^^^^

 *   :meth:`~ConstBitStream.bytealign` -- Align to next byte boundary.
 *   :meth:`~ConstBitStream.peek` -- Peek at and interpret next bits as a single item.
 *   :meth:`~ConstBitStream.peeklist` -- Peek at and interpret next bits as a list of items.
 *   :meth:`~ConstBitStream.read` -- Read and interpret next bits as a single item.
 *   :meth:`~ConstBitStream.readlist` -- Read and interpret next bits as a list of items.

Additional attributes
^^^^^^^^^^^^^^^^^^^^^

 *   :attr:`~ConstBitStream.bytepos` -- The current byte position in the bitstring.
 *   :attr:`~ConstBitStream.pos` -- The current bit position in the bitstring.


``class BitStream(BitArray, ConstBitStream)``
---------------------------------------------

This class, also known as ``BitString`` contains all of the 'stream' elements of ``ConstBitStream`` and adds all of the mutating methods of ``BitArray``.

