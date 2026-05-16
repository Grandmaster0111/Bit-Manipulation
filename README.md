# Bit Manipulation

A reference collection of bit manipulation techniques, algorithms, and common interview problems.

## Techniques Covered

### Basic Operations
```python
x & y    # AND  — keep bits set in both
x | y    # OR   — set bits set in either
x ^ y    # XOR  — toggle bits that differ
~x       # NOT  — flip all bits
x << n   # Left shift  — multiply by 2^n
x >> n   # Right shift — divide by 2^n
```

### Common Tricks

| Problem | Solution |
|---------|---------|
| Check if bit `i` is set | `(x >> i) & 1` |
| Set bit `i` | `x \| (1 << i)` |
| Clear bit `i` | `x & ~(1 << i)` |
| Toggle bit `i` | `x ^ (1 << i)` |
| Check if power of 2 | `x & (x - 1) == 0` |
| Count set bits | `bin(x).count('1')` |
| Get lowest set bit | `x & (-x)` |
| Clear lowest set bit | `x & (x - 1)` |
| Swap two numbers | `a ^= b; b ^= a; a ^= b` |

### Interview Problems

```python
# Single Number — find the element that appears once
def single_number(nums):
    return reduce(lambda a, b: a ^ b, nums)

# Missing Number (0 to n)
def missing_number(nums):
    return reduce(lambda a, b: a ^ b, range(len(nums)+1)) ^ reduce(lambda a, b: a ^ b, nums)

# Reverse bits of a 32-bit integer
def reverse_bits(n):
    result = 0
    for _ in range(32):
        result = (result << 1) | (n & 1)
        n >>= 1
    return result
```

## Resources

- [Bit Twiddling Hacks](https://graphics.stanford.edu/~seander/bithacks.html)
- [LeetCode Bit Manipulation tag](https://leetcode.com/tag/bit-manipulation/)
