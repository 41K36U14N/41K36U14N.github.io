---

title:  "Encoding systems"
date: 2024-04-23 00:00:00 +0800 
categories: [Operating systems, Encoding] 
tags: [cybersecurity, it, operating systems, encoding, unicode, binary, octal, decimal, hexadecimal] 
---

Hello and welcome, In this post we'll be taking a colorful journey through digital language. In the vibrant world of makeup and gaming, where creativity meets technology, there's a common language that underpins everything we do – binary. Whether you're mastering the art of eyeshadow blending or conquering virtual realms, understanding the basics of binary can unlock a world of possibilities. So let's dive into the colorful world of the diffrent digital languages.

Let’s look at how computers convert numbers and text to get a sense of how far [Unicode](https://41k36u14n.github.io/posts/Encoding/) has come in being an ‘all-in-one’ character encoding system. Counting on a screen usually begins with 0 rather than 1. As a result, numbering all the bits equals 255, but starting at 0 gives you 256.


### Unveiling Binary: The Language of Machines

Binary, introduced by Gottfried Leibniz, is a numerical system consisting of only two digits – 0 and 1. While this may seem simplistic, binary serves as the foundation for all digital communication, including machine processor instructions. In binary, 0 represents OFF, while 1 signifies ON, mirroring the flow of electricity through transistors in electronic devices.

In the world of makeup and gaming, binary may seem like a foreign concept, but its elegance lies in its simplicity. By leveraging binary, developers can manage logic circuits, detect electrical signal conditions, and even encode colors in digital displays.


### Understanding Binary Representation

At its core, binary is a positional numbering system, much like the decimal system we use every day. However, while decimal operates with ten digits (0 through 9), binary operates with only two digits – 0 and 1. Each digit in a binary number is called a bit, short for binary digit.

### Counting in Binary

Counting in binary follows a similar pattern to counting in decimal, but with some key differences. In decimal, when we reach 9, we increment to the next place value (adding a digit) and reset the units place to 0. Similarly, in binary, when we reach 1, we increment to the next place value and reset the current place value to 0.

Let's look at a simple binary counting sequence:

- 0
- 1
- 10 (binary for 2)
- 11 (binary for 3)
- 100 (binary for 4)
- 101 (binary for 5)
- 110 (binary for 6)
- 111 (binary for 7)
- 1000 (binary for 8)

### Binary

Performing calculation operations in binary is similar to decimal calculation, but with simpler rules due to the limited number of digits. Here are some basic binary calculation operations:

- **Addition:** Adding two binary numbers follows the same rules as decimal addition, with the only possible digits being 0 and 1. When adding two 1s, the result is 10 in binary (equivalent to 2 in decimal), and the 1 carries over to the next place value.
  
  Example:
  ```
    1101   (13 in decimal)
  + 1010   (10 in decimal)
  -------
   10111   (23 in decimal)
  ```

- **Subtraction:** Subtraction in binary follows similar principles to decimal subtraction, but with borrowing from higher place values. When subtracting a larger digit from a smaller one, borrow 1 from the next higher place value (if available).

  Example:
  ```
    1011   (11 in decimal)
  -  110   (6 in decimal)
  -------
     101   (5 in decimal)
  ```

- **Multiplication:** Multiplication in binary involves shifting and adding operations, similar to decimal multiplication. Each bit in the multiplicand is multiplied by each bit in the multiplier, and the results are added together.

- **Division:** Division in binary is analogous to long division in decimal, with repeated subtraction and shifting operations to determine the quotient and remainder.

### Binary in Computing

Binary forms the foundation of digital computing systems, where data is represented in binary form and processed using binary calculation. Inside a computer's central processing unit (CPU), binary logic gates manipulate binary data to perform calculations, execute instructions, and process information.

Understanding binary is essential for computer programmers, engineers, and anyone interested in the inner workings of digital technology. By mastering binary representation and calculation, individuals can gain insights into how computers function and leverage this knowledge to develop software, design hardware, and solve complex problems in the digital realm.

### Conclusion

Binary may seem like a simple numbering system, but its 
meaning are deep in the world of computing and technology. From counting to calculation operations, binary forms the backbone of digital communication and computation. By exploring binary representation and calculation, individuals can unlock a deeper understanding of the digital world and harness its power to innovate, create, and explore new frontiers of technology.


### Decoding Decimal and Hexadecimal: From Makeup Palettes to Color Codes

While binary is the language of machines, its counterparts – decimal and hexadecimal – offer a bridge between digital and human understanding. Decimal, our familiar base-10 numbering system, is akin to the shades in a makeup palette – each number represents a unique hue or tone.

Hexadecimal, on the other hand, adds a splash of complexity to the mix. With its base-16 numbering system, hexadecimal assigns values to digits ranging from 0 to F (representing 0 to 15 in decimal). For makeup artists and web designers alike, hexadecimal color codes are basic tools for creating stunning visual compositions. From bold blues (#0000FF) to radiant reds (#FF0000), hexadecimal codes provide a precise language for expressing color in the digital realm.


Let's dig deeper into decimal and hexadecimal coding and understand their significance in computing.

### Decimal Number System

The decimal number system, also known as base-10, is the most familiar numbering system to us, primarily because we use it in our daily lives. **It consists of ten digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9**. Each digit's value is determined by its position in the number relative to the decimal point.

#### Representation:
- Each digit in a decimal number represents a power of 10.
- For example, the number 1234 in decimal can be represented as:

```
1 * 10^3 + 2 * 10^2 + 3 * 10^1 + 4 * 10^0
= 1000 + 200 + 30 + 4
= 1234
```

Decimal numbers are intuitive for humans because we have ten fingers, making them easy to understand and work with in everyday situations.

### Hexadecimal Number System

The hexadecimal number system, often referred to as hex, is a base-16 numbering system. It uses sixteen distinct symbols: 0-9 for values 0 to 9 and A-F (or a-f) for values 10 to 15. Hexadecimal numbers are widely used in computing, especially in low-level programming and digital electronics, due to their convenience in representing binary-coded values.

#### Representation:
- Each digit in a hexadecimal number represents a power of 16.
- For example, the number 1A2F in hexadecimal can be represented as:

```
1 * 16^3 + A * 16^2 + 2 * 16^1 + F * 16^0
= 1 * 4096 + 10 * 256 + 2 * 16 + 15 * 1
= 4096 + 2560 + 32 + 15
= 6711
```

#### Conversion between Binary and Hexadecimal:
- Since hexadecimal is base-16 and binary is base-2, it is straightforward to convert between the two.
- Each hexadecimal digit corresponds to a group of four binary digits (bits).
- For example:
  - Binary: 1010 1100 1111
  - Hexadecimal: ACF

### Why Hexadecimal is Used in Computing:
1. **Compact Representation:** Hexadecimal numbers provide a more compact representation of binary values, making them easier to work with and reducing the length of binary sequences.
2. **Memory Addresses:** Memory addresses in computers are often expressed in hexadecimal, as they correspond directly to binary addresses.
3. **Color Representation:** Hexadecimal is commonly used in web design and digital imaging to represent colors, with each pair of hexadecimal digits representing the red, green, and blue components of a color.

### Conclusion:
Decimal and hexadecimal numbering systems play crucial roles in computing and digital communication. While decimal is intuitive and familiar to humans, hexadecimal offers a more compact representation of binary data, making it essential in computer programming, digital electronics, and various other fields. Understanding both systems is fundamental for anyone working with computers, as they form the basis of numerical representation in the digital world.

##### Now! on to the Octal Number System
### Octal: A Hidden Gem for File Permissions and Beyond

While decimal and hexadecimal steal the spotlight, octal quietly plays a crucial role in the world of Linux and Unix. With its base-8 numbering system, octal simplifies file permissions and system settings into concise numerical values. Instead of wrestling with lengthy command strings, developers can invoke octal numbers to grant read, write, and execute permissions with ease.

### Octal Number System

The octal number system, also known as base-8, is a numerical system that uses eight distinct digits: 0, 1, 2, 3, 4, 5, 6, and 7. Each digit's value is determined by its position in the number relative to the octal point. Octal numbers are commonly used in computing, especially in older systems, though their usage has decreased in favor of hexadecimal and binary.

#### Representation:
- Each digit in an octal number represents a power of 8.
- For example, the number 123 in octal can be represented as:

```
1 * 8^2 + 2 * 8^1 + 3 * 8^0
= 64 + 16 + 3
= 83 (in decimal)
```

### Why Octal is Used in Computing:
1. **Compact Representation:** Octal numbers provide a more compact representation of binary values compared to hexadecimal, making them useful for representing large binary sequences in a shorter format.
2. **File Permissions:** In Unix-like operating systems, octal notation is commonly used to represent file permissions. Each digit in a three-digit octal number represents the permission set for the file owner, group, and others (in that order).
   - For example:
     - 755: Owner has read, write, and execute permissions, group and others have read and execute permissions.
     - 644: Owner has read and write permissions, group and others have read permissions.
3. **System Configuration:** Octal numbers are used in some system configurations and settings, particularly in older systems where hexadecimal and binary may not be as convenient.

### Conversion between Binary and Octal:
- Since octal is base-8 and binary is base-2, it is straightforward to convert between the two.
- Each octal digit corresponds to a group of three binary digits (bits).
- For example:
  - Binary: 101 110 011
  - Octal: 567

### Conclusion:
While octal numbers are not as commonly used as decimal or hexadecimal in modern computing, they still hold significance in certain areas, such as file permissions and system configurations. Understanding octal numbering is valuable for computer programmers and system administrators, as it allows for efficient representation and manipulation of binary data in a more compact format.

### Embracing the Beauty of Diversity

In the realm of makeup and gaming, diversity is celebrated as a cornerstone of creativity. Similarly, the world of binary and its numerical companions embrace diversity in all its forms. Whether you're a makeup enthusiast experimenting with vibrant colors or a gaming aficionado exploring immersive worlds, binary provides a common language that transcends boundaries and fosters connection.

### Conclusion: Beauty in Every Byte

As we journey through the colorful landscape of makeup and gaming, let's not forget the beauty of binary that underpins it all. From the shimmering pixels on a screen to the intricate shades of a makeup palette, binary is woven into the fabric of our digital lives. So whether you're blending eyeshadows or conquering virtual quests, remember that behind every hue and pixel lies the elegant simplicity of binary – a language that speaks volumes in every byte.
