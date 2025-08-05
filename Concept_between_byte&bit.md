This chapter is made for a sharp and important distinction from a question:
>**“When Notepad encounters the bytes of a PNG file”**   
>Why you said **the bytes of a PNG file**, not **the bit of the binary code** of PNG file?

1. **Fundamental Unit of Storage and Processing**: A `byte `is a group of 8 bits. This is the most common and fundamental unit for measuring file sizes, memory, and data transfer. A single character ina text file (using a standard encoding like ASCII) is represented by one byte. File sizes are almost always measured in kilobytes, megabytesm gigabytes, etc., all of which aare based on the byte.

2. **Notepad's Reading Process**: a program like Noteepad reads a file from storage, it doesn't read it ont bit at a time. It reads it in chunks(blocks), typically in whole bytes. It processes the file's contents byte by byte.This is because ***a byte is the standard addressable unit of memory***.

3. **Meaningful Chunks**: The data within a PNG file, as we discussed, is organized into meaningful chunks. For example:
- The file's header is a specific sequence of bytes.
- The width and height of the image are often stored as 4-byte integers.
- The color information for a single pixel might take up 3 or 4 bytes (e.g., one byte for red, one for green, one for blue, and sometimes one for transparency).

So, while the bytes themselves are ultimately made of bits, it's more accurate to describe Notepad;s interaction with the file at the byte level. It's reading a sequence of `01000001`, `01000010`, etc., and trying to find the corresponding character for each 8-bit sequence.

Think of this way: a car is made of atoms, but when we talk about its structure, we talk about parts like the engine, wheels, and chassis. Similarly, a file is made of bits, but when we discuss its content and how programs interact with it, we often talk in terms of the more meaningful unit, the byte.

So, saying "the bytes of a PNG file" is a more technically precise way of describing the data in the context of how a program like Notepad processes it.