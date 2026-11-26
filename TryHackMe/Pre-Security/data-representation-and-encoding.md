# Data Representation and Encoding

## Colours

- Colours, like everything else in a computer, are represented as 0s and 1s.
- You can combine 3 bits, one each for red, green and blue, to get 8 different colours (2 × 2 × 2 = 8).
- If you use more bits for each colour, you get finer control over the shade, so you can represent many more colours.
- Your computer uses 24 bits to represent a standard colour, which allows for about 16.7 million distinct colours.
- It uses 8 bits each for red, green and blue.

## Characters

- Characters are just numbers with agreed meanings. That agreement is called an **encoding**.
- One of the earliest standards for encoding English letters was **ASCII**.
- ASCII stands for American Standard Code for Information Interchange.
- It's a character encoding from 1963 that uses the numbers 0-127 to represent English letters, digits, punctuation and some control characters.
- When you save text, or print it with tools like `echo`, a newline character (`\n`) is often added at the end by default.

## Hexadecimal

- Reading long binary numbers is slow and easy to get wrong, so we prefer hexadecimal (hex) digits.
- Each hex digit represents a group of 4 bits.
- It's uncommon to use decimal digits for this. Hex is the usual choice when we want to show the bits.

## Other Languages

- The problem was that ASCII didn't support other European languages.
- So the ISO/IEC 8859 series of international standards was created. Each standard covered a set of languages:
    - **ISO-8859-1 (Latin-1)**: Covered **Western European languages** like German (ß, ü), French (é, ç), Spanish (ñ, ¿), Italian, Portuguese, Catalan and Nordic languages (e.g. Icelandic ð/Ð). [Character list](https://www.charset.org/charsets/iso-8859-1)
    - **ISO-8859-2 (Latin-2)**: Covered **Central/Eastern European languages** like Polish (ł, ń), Czech (č, ř), Hungarian (ő, ű), Croatian (đ), Romanian (ș, ț) and Slovak. [Character list](https://www.charset.org/charsets/iso-8859-2)
- So if a document is saved using ISO-8859-1 but later read as if it were ISO-8859-2, non-English letters will likely show up as the wrong characters.

## Unicode

- Unicode is a universal character encoding standard.
- It gives a unique number (code point) to characters from all modern and historical writing systems worldwide.
- It allows text in many different languages to be shared, processed and displayed correctly.

### UTF-8
- Very common on the web.
- It uses a different amount of space for each character, based on need: between 1 and 4 bytes.

### UTF-16
- Uses either 2 or 4 bytes per character.
- Characters like emojis, which don't fit in 2 bytes, use 4 bytes.

### UTF-32
- Uses 4 bytes for every character.
- This is where the most space is wasted.
