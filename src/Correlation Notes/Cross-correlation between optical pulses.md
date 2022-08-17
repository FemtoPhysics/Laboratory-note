# Cross-correlation between optical pulses

## 1.1 The arrival time depends on the incident angle of a pulse
First, assume an ideal plane-wave pulsem which can be described in
$$
    E_{1}\left(\mathbf{r},t\right) = \exp\left(\mathbf{k_{1} r} - \omega_1 t \right)
$$
The field of a pulse $E_{1}$ shine on a nonlinear crystyal which is located at $x-y$ plane ($z = 0$ plane) with the angular momentum $k_{x}$.
$$\begin{align} k_{x} &= k_{1} \sin \theta_{1}
\\
k_{y} &= 0
\\
k_{z} &= k_{1} \cos \theta_{1} 
\end{align}$$

As a result, the field of pulse $E_{1}$ can be rewritten in
$$
    E_{1}\left(x, y, z=0, t \right) = \exp \left(k_{x} x + k_{y} y - \omega_{1} t \right)
$$
Thus, the condition of the wavefront $E_{1}$ arriving $x-y$ plane can be simplfied as $k_{x} x - \omega_1 t_{1} =0$. And, the time delay of the wavefront $E_{1}$ arriving $x-y$ plane can be noted as
$$
t_{1} = \frac{k_{1} \sin \theta_1}{\omega_{1}} x= \frac{x}{c}\sin \theta_{1}
$$

## 1.2 The time delay beteween the arrival times of pulses
For the general cases of autocorrelation, there have two independent pulses, $E_{1}$ and $E_{2}$, with different incident angle, $\theta_{1}$ and $\theta_{2}$, respectively. As a results, the overall time delay between two pulses can written in
$$
\Delta t = t_{1} - t_{2} = \frac{x}{c} \left( \sin \theta_{1} + \sin \theta_{2} \right)
$$
which imply the time overlapping is independent of the frequency of pulses, $\omega_{1}$ and $\omega_{2}$. 

In a simple case, when the normal direction of plane (the surface of nonlinear crystal) is evenly divided by two pulses, which means $\theta_{1}=\theta_{2}=\frac{\theta}{2}$, the time delay can be simplfied as $\Delta t = 2 \sin \theta \frac{x}{c}$. 

- When $\theta = 90^o$, time delay is 47 picosecond per centimeter. 
- When $\theta = 45^o$, time delay is 25 picosecond per centimeter. 
- When $\theta = 10^o$, time delay is 5.8 picosecond per centimeter. 
- When $\theta = 1^o$, time delay is 0.58 picosecond per centimeter. 

## 2.1 The cross-correlation depends on the beamsize of pulses
