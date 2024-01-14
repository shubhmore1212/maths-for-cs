Using Booleans:

```
class Character{
public bool HasMagic { get; set; }
public bool HasIntelligence { get; set; }
public bool IsInvisible { get; set; }
}
```

Each boolean variable (HasMagic, HasIntelligence, IsInvisible) would generally require 1 byte of memory, resulting in a total of 3 bytes for the three variables.

Using Integers:

```
// Existing powers
public const int HasMagic = 1;
public const int HasIntelligence = 2;
public const int IsInvisible = 4;


class Character
{
public int Powers { get; set; }
}

```

In this case, the Powers integer requires either 4 or 8 bytes, depending on the platform. However, this single integer can represent multiple boolean flags efficiently using bitwise operations. For example, the combination of HasMagic, HasIntelligence, and IsInvisible can be represented as a single integer.

Bitwise operations are generally faster than logical operations on individual boolean values. For instance, checking whether a character has a specific combination of powers using bitwise AND, OR, or XOR operations can be more efficient than checking each boolean value separately.

With integers, you can easily represent combinations of powers and modify them using bitwise operations. This flexibility is advantageous in scenarios where characters can acquire or lose powers dynamically during gameplay.

Storing powers as integers simplifies the representation of characters in data structures such as arrays or databases. The integer value can be directly stored or transmitted, reducing the complexity of managing multiple boolean fields. This simplicity can enhance the efficiency of data storage and retrieval operations.

Using integers and bitwise operations to represent powers is that it provides a flexible and extensible way to accommodate new powers without significantly altering the structure of the class.

Bit masking is a technique in computer programming that involves using bitwise operations to manipulate specific bits within an integer or a set of bits in a binary representation. This technique is commonly employed to extract, set, clear, or toggle specific bits within a binary number.

```<< => left shift operator
for eg: 1<<0 => 0001
        1<<2 => 0100```

Setting a Bit:
To set a particular bit to 1, you use the bitwise OR (|) operation with a value that has only that bit set to 1 and all other bits set to 0.

`originalValue |= (1 << bitPosition);`

Clearing a Bit:
To set a particular bit to 0, you use the bitwise AND (&) operation with a value that has only that bit set to 0 and all other bits set to 1.

`originalValue &= ~(1 << bitPosition);`

Toggling a Bit:
To toggle the value of a particular bit (change 0 to 1 and vice versa), you use the bitwise XOR (^) operation with a value that has only that bit set to 1 and all other bits set to 0.

`originalValue ^= (1 << bitPosition);`

Checking if a Bit is Set:
To check if a particular bit is set (equals 1), you use the bitwise AND (&) operation with a value that has only that bit set to 1 and all other bits set to 0.

`isSet = (originalValue & (1 << bitPosition)) != 0;`
