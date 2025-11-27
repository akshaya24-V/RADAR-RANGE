# RADAR-RANGE
# AIM
To study the variation of radar range with respect to transmitted power, antenna gain, and minimum detectable power using the radar range equation.

# APPARATUS / SOFTWARE REQUIRED
PC INSTALLED WITH SCILAB

Computer system with plotting capability

# THEORY
The radar range equation expresses the relationship between transmitted power, antenna gains, wavelength, radar cross section, and receiver sensitivity to determine the maximum distance at which a radar can detect a target.

The parameters involved are:

Pt – Transmitted power (W)

Gt – Transmitting antenna gain

Gr – Receiving antenna gain

L – Wavelength (m)

sigma – Radar cross section of the target (m²)

Pmin – Minimum detectable signal power (W)

R – Maximum radar range (m)

From the radar range equation,

The range increases with transmitted power.

The range increases with antenna gain.

The range decreases as minimum detectable power increases.

Thus, the radar’s performance mainly depends on transmitted power, antenna efficiency, and receiver sensitivity.

# PROCEDURE
Initialize constants: Speed of light c = 3 × 10⁸ m/s Transmitting gain Gt = 50 Receiving gain Gr = 50 Wavelength L = 0.03 m Radar cross section sigma = 10 Minimum detectable power Pmin = 1 × 10⁻⁹ W

Case 1 – Variation with transmitted power: Vary Pt from 0 to 5 W in steps of 0.05 and calculate the radar range R. Plot R versus Pt.

Case 2 – Variation with antenna gain: Fix Pt = 1 W and vary gain G from 0 to 5 in steps of 0.05. Plot R versus G.

Case 3 – Variation with receiver sensitivity: Fix Pt = 1 W and vary Pmin from 1 × 10⁻¹² to 1 × 10⁻⁸ W. Plot R versus Pmin.

Display all three plots using the subplot command for comparison.

# PROGRAM:

Gt = 35;

Gr = 35;

L = 1;

sigma = 1;

Pmin = 1e-13;

Pt = 0.1:0.1:10.1;

R = (((Pt .* Gt .* Gr .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin))).^(1/4);

subplot(3,1,1);

plot(Pt, R);

G = 1:1:50;

Pt = 2;

R = (((Pt .* G .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin))).^(1/4);

subplot(3,1,2);

plot(G, R);

Gt = 35;

Gr = 35;

Pmin = logspace(-15, -10, 50);

R = (((Pt .* Gt .* Gr .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin))).^(1/4);

subplot(3,1,3);

plot(Pmin, R);


# OUTPUT WAVEFORM:

<img width="1600" height="853" alt="image" src="https://github.com/user-attachments/assets/d808aef7-42c8-42e6-908a-ac1c8c9bb509" />



# THEORETICAL CALCULATION:

<img width="758" height="1280" alt="image" src="https://github.com/user-attachments/assets/92f52268-0e91-4dc0-9542-d8e36fa3fa49" />



# RESULT
As transmitted power increases, radar range also increases.

As antenna gain increases, radar range increases.

As minimum detectable power increases (receiver becomes less sensitive), radar range decreases.
