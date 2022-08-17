# DSP EP1 - Deal with Oscillations
Author: [yctai](brianyjtai1994@gmail.com)
- - -
It is common to encounter a damped oscillation in signal processing of pump-probe spectroscopy. This note is a showcase to demonstrate how to deal with signals that contain damped oscillations.

## Case 1: Single Oscillation

1. First, we start with a simple oscillation with a frequency of $f = 0.5$ as
    $$
    y_{1} \left(t\right) =
        \sin \left(2\pi f t\right)
    $$
2. Second, we modulate the signal $y_{1}$ with a damping constant $\tau = 2.5$ as
    $$
    y_{2} \left(t\right) =
        e^{-t / \tau} \, \sin \left(2\pi f t\right)
    $$
3. Third, we pad the signal $y_{2}$ with another exponential decay as
    $$
    y_{3} \left(t\right) =
        1.5 \, e^{-t / 2} +
        e^{-t / \tau} \, \sin \left(2\pi f t\right)
    $$

![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/DSP%20Notes/img/fft-demo1.png "FFT demo of a damped oscillation stands on an exponential decay.")

1. If we compute the Fourier transform correctly, the power spectrum will accurately reflect the **amplitude** and the **frequency** of $y_{1}\left(t\right)$.
2. Although the oscillation is modulated in signals $y_{2}\left(t\right)$ and $y_{3}\left(t\right)$, the Fourier power spectra can still output the frequency of $f = 0.5$.
3. <font color=firebrick>**Note that**</font> in the phase spectra, the phases of signals $y_{2}\left(t\right)$ and $y_{3}\left(t\right)$ share the same value of $\sim -1.5$ at the frequency $f = 0.5$.

## Case 2: Linear Combination

1. Again, we start with a simple oscillation with frequencies of $f_{1} = 0.5$ and $f_{2} = 1.0$ as
    $$
    y_{1} \left(t\right) =
        \sin \left(2\pi f_{1} t\right) +
        0.8 * \sin \left(2\pi f_{2} t\right)
    $$
2. We modulate the signal $y_{1}$ with damping constants $\tau_{1} = 2.5$ and $\tau_{2} = 5$ as
    $$
    y_{2} \left(t\right) =
        e^{-t / \tau_{1}} \, \sin \left(2\pi f_{1} t\right) +
        0.8 * e^{-t / \tau_{2}} \, \sin \left(2\pi f_{2} t\right)
    $$
3. Then, we pad the signal $y_{2}$ with another exponential decay as
    $$
    y_{3} \left(t\right) =
        1.5 \, e^{-t / 2} +
        e^{-t / \tau_{1}} \, \sin \left(2\pi f_{1} t\right) +
        0.8 * e^{-t / \tau_{2}} \, \sin \left(2\pi f_{2} t\right)
    $$

![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/DSP%20Notes/img/fft-demo2.png "FFT demo of a damped oscillation stands on an exponential decay.")

1. **Obviously**, the Fourier power spectrum correctly returns the amplitudes and the frequencies of $y_{1}\left(t\right)$.
2. The Fourier power spectra can output the interested frequencies $f_{1} = 0.5$ and $f_{2} = 1.0$ in both $y_{2}$ and $y_{3}$ signals as usual.
3. <font color=firebrick>**The phases**</font> of signals $y_{2}\left(t\right)$ and $y_{3}\left(t\right)$ share the same values of $\sim -1.5$ at the frequencies $f_{1}$ and $f_{2}$, respectively.

## Case 3: Oscillation with Envelope

1. Now, we start with a beating oscillation with a sum-frequency of $f_{1} + f_{2} = 0.75$ and a difference-frequency of $f_{1} - f_{2} = 0.5$ as
    $$
    y_{1} \left(t\right) =
        \sin \big[2\pi \left(f_{1} - f_{2}\right) \, t\big] \cdot
        \sin \big[2\pi \left(f_{1} + f_{2}\right) \, t\big]
    $$
2. Then, we modulate the signal $y_{1}$ with a damping constant $\tau = 2.5$ as
    $$
    y_{2} \left(t\right) =
        e^{-t / \tau} \cdot \Big\lbrace
            \sin \big[2\pi \left(f_{1} - f_{2}\right) \, t\big] \cdot
            \sin \big[2\pi \left(f_{1} + f_{2}\right) \, t\big]
        \Big\rbrace
    $$
3. In the last step, we pad the signal $y_{2}$ with another exponential decay as
    $$
    y_{3} \left(t\right) =
        1.5 \, e^{-t / 2} +
        e^{-t / \tau} \cdot \Big\lbrace
            \sin \big[2\pi \left(f_{1} - f_{2}\right) \, t\big] \cdot
            \sin \big[2\pi \left(f_{1} + f_{2}\right) \, t\big]
        \Big\rbrace
    $$

![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/DSP%20Notes/img/fft-demo3.png "FFT demo of a damped oscillation stands on an exponential decay.")

1. Before the discussion, we first rewrite the signal $y_{1}\left(t\right)$ as
    $$
    y_{1} \left(t\right) =
        \dfrac{1}{2} \cos \left(2\pi f_{2} \, t\right) -
        \dfrac{1}{2} \cos \left(2\pi f_{1} \, t\right)
    $$
2. The Fourier transform of $y_{1}\left(t\right)$ clearly shows two frequencies of $0.25$ and $1.25$, with both amplitudes equal to $0.5$.
3. The Fourier power spectra of both $y_{2}$ and $y_{3}$ signals still contain the information of frequencies $f_{1}$ and $f_{2}$, which we are interested in as in the previous cases.
4. <font color=firebrick>**The phases**</font> of signals $y_{2}\left(t\right)$ and $y_{3}\left(t\right)$ **no longer** share the same values at the frequencies $f_{1}$ and $f_{2}$.

## Conclusion: Generic Principle

1. <font color=firebrick>**Do NOT**</font> use your eyes to determine the oscillations in the time series data.
2. The Fourier transform of the **equidistant** time series will honestly return all the hidden oscillations. You do **NOT** need to do a curve fitting to determine where the oscillations are.
3. The phase spectra can help you to decide which mathematical formula you should use if you read it carefully. 