# What is Lock-in Amplifier

![[lock-in.png]]


• Lock-in amplifiers are used to detect and measure very small AC signals-all the way down to a few nano-volts.


• Even when the small signal is obscured by noise sources many thousands of times larger.


• Lock-in amplifiers use a technique known as phase-sensitive detection to single out the component of the signal at a specific reference frequency and phase.


• Noise signals, at frequencies other than the reference frequency, are rejected and do not affect the measuremen


# How Lock-in Amplifier work

## phase-sensitive detection (PSD)

Consider one signal
$$
	V_{sig}sin(ω_{r}t+θ_{sig})
	$$
And one reference signal
$$
	V_{L}sin(ω_{L}t+θ_{ref})
	$$
  where V is the signal amplitude, ω is the signal frequency, and θ is the signal’s phase.

The output of the PSD is simply the product of two sine waves.
$$
	V_{psd}=V_{sig}V_{L}sin(ω_{r}t+θ_{sig})sin(ω_{L}t+θ_{ref})
	
	$$
	$$
	=\dfrac{1}{2} V_{sig}V_{L}cos([ω_{r}-ω_{L}]t+θ_{sig}-θ_{ref})-\dfrac{1}{2} V_{sig}V_{L}cos([ω_{r}+ω_{L}]t+θ_{sig}+θ_{ref})
	$$

  the PSD output is two AC signals.

When the $ω_{r}=ω_{L}$ ,
$$
	V_{psd}=\dfrac{1}{2}V_{sig}V_{L}cos(θ_{sig}-θ_{ref})-\dfrac{1}{2} V_{sig}V_{L}cos([ω_{r}+ω_{L}]t+θ_{sig}+θ_{ref})
	$$

  <font color=red>"the first part is time independent signal".</font>
If the PSD output is passed through a low-pass filter
$$
	V_{psd}=\dfrac{1}{2}V_{sig}V_{L}cos(θ_{sig}-θ_{ref})
	$$
This is a very nice signal "it is a DC signal proportional to the signal amplitude".

Now, let's see the schematic for Lock-in.

![[schematic for Lock-in.png]]

###### For a very small AC signal of known frequency, Lock-in will make it pass a band-pass filter first  for cut noise, then use a reference signal to product it, and chang the reference wave's phase until the out put is DC signal.

This is how lock-in amplifiter work.

# Appendix-Pump-Probe experiment

## Pump-Probe
The main point of the pump-probe experiment is two femtosecond-pulse arrivals in the sample at the same time, then making a delay for one of them and seeing the difference ($\dfrac{∆A}{A}$).

![[schematic for pump probe.png]]

Image that, two events(pulse) happen in 1 ns.

![[Two events image.png]]

BUT! <font color=firebrick>**Note that**</font> The detector's exposures time is microsecond level.

And two event will repeat again and again in detector's exposures time, finaly you will get a volt every few microsecond.

![[about detector.png]]

Then, the Lock-in Amplifier collect signal from detector.

//The square wave signal is based on AOM (kind of optical chopper), more detail you can finding from UDL master student's paper.

![[the signal lock in get.png]]

So far so good, BUT in real case the signal not strong like that and a lot of noise will cover it.

![[detector output.png]]

//This is why we need Lock-in Amplifier.

![[schematic for Lock-in.png]]