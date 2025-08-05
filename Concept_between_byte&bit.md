This chapter is made for a sharp and important distinction from a question:
>**“When Notepad encounters the bytes of a PNG file”**   
>Why you said **the bytes of a PNG file**, not **the bit of the binary code** of PNG file?

1. **Fundamental Unit of Storage and Processing**: A `byte `is a group of 8 bits. This is the most common and fundamental unit for measuring file sizes, memory, and data transfer. A single character ina text file (using a standard encoding like ASCII) is represented by one byte. File sizes are almost always measured in kilobytes, megabytesm gigabytes, etc., all of which aare based on the byte.

2. Notepad's Reading Process: a program like Noteepad reads a file from storage, it doesn't read it ont bit at a time. It reads it in chunks(blocks), typically in whole bytes. It processes the file's contents byte by byte.This is because ***a byte is the standard addressable unit of memory***.

3. Meaningful Chunks: