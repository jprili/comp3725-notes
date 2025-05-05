# Appendix

Other background information and outside references can be found here.

## Hamming Error Correction
See this 3Blue1Brown's video on [Hamming Codes](https://www.youtube.com/watch?v=X8jsijhllIA) to understand the motivation behind error codes. 

[ADD STUFF HERE]

### Hamming Distance
In a nutshell, the hamming distance can be programmatically written like so:

```ts title="typescript"
/**
 * Calculates the distance between Arrays s1 and s2.
 * @param s1 an array of T
 * @param s2 another array of T
 * @returns the number of differing elements.
 *          if s1 and s2 have different lengths, -1.
 */
function hammingDistance<T>(s1: Array<T>, s2: Array<T>): number {
    // guard case
    if (s1.length != s2.length) {
        return -1;
    }
    let  count: number = 0; // set accumulator
    for (let i: number = 0; i < s1.length; ++i) {
        count += Number(s1[i] != s2[i]); // cast to number
    }
    return count;
}
```

## Math

### Trigonometry

### Logarithms
