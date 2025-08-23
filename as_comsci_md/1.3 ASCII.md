# 1.3 ASCII
(American standard code for information interchange)

## Character sets
- many different character sets exist
- charakter sets map symbols/characters to binary numbers
- used to be non-standardized, 7bit, and different for each language
- Original ASCII was 128 characters (7 bit) but later extended: 256 characters (1 byte)

## Encoding Tables
- characters encoded in binary
- basically a "lookup table"
- characters are grouped
    - ↳ if 97=a, then 100=d always

## Unicode
- uses 16 bits, way larger than ASCII (extended)
- aims to cover all symbols and characters ever used
- has 120,000+ characters
- actually one Unicode set can contain just 65,536 characters
- UTF-8 is the most popular Unicode set

## Converting from ASCII 7-bit to 8-bit
- 8-bit ASCII is created so that 7-bit ASCII can easily be transformed / be used along 8-bit ASCII
- eg. 7-bit 'a': `1100001`
- 8-bit 'a': `11100001`
- just add a 1 bit to the most left-hand side

## Some key-facts about ASCII
- there are graphic codes and control codes
    - ↳ used to assist in data transmission and representation (formatting)
- The codes are sequential; code for '7' + 1 = code for '8'
- The codes for upper- and lowercase letters only differ in one bit
- ASCII numbers are only used in the context of stored, displayed, or printed text.

## Unicode UTF-8
- most popular Unicode character set
- mainly includes 1 byte characters (therefore the '8'), but also some characters using 2, 3, or 4 bytes
- ASCII is also contained in UTF-8, and written with a 0 for the 8th bit
- Byte Formats for Unicode UTF-8
    - ASCII: `0???????`
    - 2 byte symbol: `110?????` `10??????`
    - 3 byte symbol: `1110????` `2x 10??????`
    - 4 byte symbol: `11110???` `4x 10??????`
    > number of leading '1', followed by a '0' determine number of bytes coding for the character
    > following bytes are indicated by a leading '10'
- All the `?` bits are used to code for characters, so eg, the three-byte format allows for 11 coding bits, so $$2^{11}$$ possibilities

## Question 1.02
What characters would be included in a 6-bit character set?
$$2^6 = 64$$ characters
$$26 \times 2 = 52$$
$$52 + 10 = 62$$
This is just enough for...
- upper and lowercase letters
- full set of denary numbers
- space character, enter character
missing: symbols, emojis, formating/instructional characters