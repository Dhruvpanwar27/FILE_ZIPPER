# FILE_ZIPPER
This project is based on Huffman Coding, a lossless, bottom-up compression algorithm. It can compress and decompress any text files.

To learn more about Huffman Coding and its applications in Information Theory read this article.

Implementation in Project
Huffman coding is a lossless data compression algorithm that assigns variable-length codes to input characters, with shorter codes assigned to more frequent characters. The main goal of your project is to compress and decompress files using Huffman coding.

## Project Breakdown:

## Step 1: Compression (encode.cpp):

`Input` : The program takes two arguments: an input file (argv[1]) and an output file (argv[2]).

## Create Frequency Table:

The huffman class is initialized with the input and output filenames.

The `createArr()` method initializes an array of Node objects to store frequency information for each character.

`createMinHeap()` reads the input file and counts the frequency of each character, storing it in a priority queue (min-heap).

## Build Huffman Tree:

`createTree()` builds the Huffman tree by combining nodes based on their frequency.

The tree is then traversed, and the createCodes() method assigns a binary code to each character in the tree.

## Encoding:

The `saveEncodedFile()` method generates the encoded file, which includes:

The Huffman tree’s structure (meta-data).

The binary codes for characters in the input file.

The encoded output is saved as a binary file, which is compressed.

## Step 2: Decompression (decode.cpp):

`Input` : The program takes the encoded file and a destination file to save the decompressed data.

## Rebuild Huffman Tree:

`getTree()` reconstructs the Huffman tree from the meta-data stored in the encoded file.

## Decoding:

The `saveDecodedFile()` method reads the binary data from the encoded file.

Using the reconstructed Huffman tree, it decodes the binary stream back into the original characters and writes the result to the output file.

## Huffman Class Methods Overview:
`createArr()` : Initializes an array of Node objects (one for each ASCII character, initialized with a frequency of 0).

`createMinHeap()` : Reads the input file to count the frequency of each character and pushes them into a priority queue (min-heap).

`createTree()` : Builds the Huffman tree by repeatedly merging the two least frequent nodes in the heap until only one node (the root) remains.

`createCodes()` : Traverses the Huffman tree and assigns binary codes to each character.

`saveEncodedFile()` : Writes the encoded file, including the meta-data (Huffman tree) and the encoded data.

`saveDecodedFile()` : Reads the encoded file, reconstructs the Huffman tree, and decodes the binary data back to its original form.


## Program Flow:

When you run encode.cpp, the program reads the input file, compresses it using Huffman coding, and saves the result in an encoded file.

When you run decode.cpp, the program takes the encoded file, reconstructs the Huffman tree, and writes the decompressed original content to a new file.



## How to run this project

## Compile the Code

Run these command in the terminal :

`g++ -o encode encode.cpp huffman.cpp`

`g++ -o decode decode.cpp huffman.cpp`

This will create two executable files.

encode (for compression)

decode (for decompression)

## Run Compression (Encoding)

If your input file is named `inputFile.txt`, run:

`./encode inputFile.txt encoded.huf`

This will compress `inputFile.txt` into `encoded.huf`.

The compressed data will be saved in `encoded.huf`.

## Run Decompression (Decoding)

To decompress `encoded.huf` back into a readable file `(e.g., outputFile.txt)` , run:

`./decode encoded.huf outputFile.txt`

