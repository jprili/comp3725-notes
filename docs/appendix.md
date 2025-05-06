# Appendix

Other background information and outside references can be found here.

## Hamming Codes

Hamming Codes is a way to encode a bit string in such a way
that a computer will be able to detect up to two bit-flips
and correct up to a single bit flip.

It leverages several parity bits (1) in specific positions to pinpoint wherei the bit-flip is located, 
and therefore flip the bit again to correct it.
{ .annotate } 

1. If a string of bits have even `1`s, 
   the parity is `0`, `1` otherwise.

See the note below for more information.

!!! note
    Check out 3Blue1Brown's video on 
    [Hamming Codes](https://www.youtube.com/watch?v=X8jsijhllIA)
    to understand the motivation behind the methodology and
    how it works. 

### Hamming Distance
The Hamming Distance Measures how different two messages of similar length are. It can be programmatically written like so:

```ts title="TypeScript"
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

These are the mathematical rules/identities that we are
going to use.

### Trigonometry

Imagine a circle with a radius of $r = 1$,
lying on a 2-dimensional plane with its centre on the origin.
With any angle $t$, the coorindates of any point on the circle's edge can be expressed as

$$
\begin{align*}
    c_x(t) &= \cos(t) \\
    c_y(t) &= \sin(t)
\end{align*}
$$ 

??? note "Show illustration"
    <figure markdown="1" style="width:25%; height:25%;">
    ![Unit Circle](res/unit-circle.svg)
    </figure>

.
$$
    \sin(x) = \frac{\text{opposite}}{\text{adjacent}}
$$

### Logarithms

$$
\begin{equation}
    \log_b(b) = 1
\end{equation}
$$
