# Introduction to The Physical Layer
Let's take a look at the representation of bits in the physical sense,
in other words, how bits are embedded into properties of signals.

## Data
Data is any collection of values that can be used to convey information.
They can either be (1) analogue/continuous or (2) digital/discrete.

## Signals
Signals are the concrete representations of data.
Since they are representations, they can also be analog or digital.

Due to the continuous nature of analogue signals,
there is an uncountable amount of intensity
levels they can have over some period of time.
Conversely, digital signals can only have a set number of values
due to the signals being discrete.

Theoretically, analogue signals *could* represent an infinite
amount of data.
However the laws of physics, measurement theory, and hardware resolution
prevent us from being able to do so. 

### Periodicity
Signals can be:

* **periodic**: have a measurable timeframe (period) 
                wherein the signal completes a pattern
                within it and goes on subsequently.
* **non-periodic**: if the signal is not periodic. 

## Period and Frequency
The **period** $T$ is the amount of time (usually in seconds)
a signal takes to complete one cycle.
**Frequency** $f$, on the other hand, is the number of cycles
completed in one second.

Essentially, period is the inverse of frequency, and vice versa:

$$
T = \frac{1}{f}
$$

## More on Analog Signals
Periodic analog signals can be

* **simple**: just a sine wave.
* **composite**: a signal composed of several sine waves of differing frequencies (1). 
    { .annotate } 

    1. see [Fourier Transform](https://simple.wikipedia.org/wiki/Fourier_transform)

## Time and Frequency domain

Read [Trigonometry](appendix.md/#trigonometry) for pre-requisite reading.

## Bit Length

## From Digital to Composite

