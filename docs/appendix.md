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

Imagine a circle with a radius of $r$,
lying on a 2-dimensional plane with its centre on the origin.
With any angle $t$, the coorindates of any point on the circle's edge can be expressed as

$$
\begin{align*}
    c_x(t) &= r\cos(t) \\
    c_y(t) &= r\sin(t)
\end{align*}
$$ 

??? note "Unit Circle $r = 1$"
    <figure markdown="1" style="width:25%; height:25%;">
        ![Unit Circle](res/unit-circle.svg)
    </figure>

In this course we will focus mostly on the sine and cosine waves,
as radio signals encode information via their properties: amplitude $A$,
frequency $f$, phase shift $\phi$, and offset $c$.
We can rewrite the sine function to show where these properties lie.
$$
    s(t) = A \sin(2\pi f t + \phi) + c
$$

$A$ determines how tall the wave is.  
$2\pi f$ (1) decides how frequent the peaks/troughs are.
{ .annotate }

1. The $2 \pi$ factor is there from the fact that every $2 \pi$ radians
   completes the cycle. Say $f = 1, \phi = 0$. If $t = 1$, then $sin(2 \pi) = 0$.
   It is a more convenient way to characterise the wave.

$\phi$ is the phase shift. This translates the wave to the left or right.

!!! warning "Be careful about shifts!"

    A positive $\phi$ means a left shift, right otherwise.

    $$
        \text{shift} 
        = \begin{cases}
            \text{right} & \phi < 0 \\
            \text{left}  & \phi > 0 \\
            \text{none}  & \phi = 0
        \end{cases}
    $$

$c$ is the vertical shift.

Here are identities in Forouzan's appendix.

<figure markdown="1">
| name | formula |
| ---- | ------- |
| Pythagorean | $ \sin^2(x) + \cos^2(x) = 1 $ |
| even/odd | $\sin(-x) = -\sin(x)$ <br/> $\cos(-x) = \cos(x)$ |
| sum | $\sin(x + y) = \sin(x)\cos(y) + \cos(x)\sin(y)$ <br/> $\cos(x + y) = \cos(x)\cos(y) - \sin(x)\sin(y)$|
| difference | $\sin(x - y) = \sin(x)\cos(y) - \cos(x)\sin(y)$ <br/> $\cos(x - y) = \cos(x)\cos(y) + \sin(x)\sin(y)$|
| product to sum | $\sin(x)\sin(y) = \frac{1}{2}[\cos(x - y) - \cos(x + y)]$ <br/> $\cos(x)\cos(y) = \frac{1}{2}[\cos(x - y) + \cos(x + y)]$ <br/> $\sin(x)\cos(y) = \frac{1}{2}[\sin(x + y) + \sin(x - y)]$ <br/> $\cos(x)\sin(y) = \frac{1}{2}[\sin(x + y) - \sin(x -y)]$|
</figure>

### Logarithms

Logarithms answers the question "what exponent should I raise $b$ to to get $x$?"
Symbolically, it is written as

$$
\begin{equation*}
    b^y = x \rightarrow \log_b(x) = y
\end{equation*}
$$

In essence, it is the inverse of the exponential function.

#### Properties

Since, the output of $\log$ is an exponent,
so its properties are similar to that of one.

$$
    \begin{align*} 
        \log_b(1) &= &0 \\
        \log_b(b) &= &1 \\
        \log_b\left(\frac{x}{y}\right) &= &\log_b(x) -\log_b(y) \\
        \log_b(xy) &= &\log_b(x) + \log_b(y) \\
        \log_b(x^{y}) &= &y\log_b(x) \\
        \log_b(y) &= &\frac{\log_c(y)}{\log_c(b)}
    \end{align*}
$$

