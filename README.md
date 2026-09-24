# SIMULATION-OF-AUTOCORRELATION-AND-PSD-USING-SCILAB---T1---M4---ODD
# SIMULATION OF AUTOCORRELATION AND PSD USING SCILAB

## AIM

To simulate the auto-correlation function and Power Spectral Density (PSD) of a cosine signal using Scilab.

## EQUIPMENTS NEEDED

* Computer with i3 Processor
* SCI LAB

## THEORY

The Wiener-Khinchin theorem states that the power spectral density of a wide sense stationary random process is the Fourier transform of the corresponding autocorrelation function.

### Power Spectral Density (PSD)

$$
S_{XX}(\omega) = FT[R_{XX}(\tau)] = \int_{-\infty}^{\infty} R_{XX}(\tau) e^{-j\omega\tau} d\tau
$$

### Autocorrelation Function (ACF)

$$
R_{XX}(\tau) = IFT[S_{XX}(\omega)] = \frac{1}{2\pi} \int_{-\infty}^{\infty} S_{XX}(\omega) e^{j\omega\tau} d\omega
$$

## ALGORITHM

### 1. Define Signal:
Define time vector $t = 0:0.01:2\pi$ and cosine signal $x(t) = 8 \cos(4t)$.

### 2. Compute Autocorrelation:
Compute the autocorrelation function using `xcorr(x, x)`.

### 3. Compute FFT & Power Spectral Density:
Compute the Fourier transform of the autocorrelation and the signal power spectrum $|FFT(x)|^2$.

### 4. Plot Results:
Display the input signal, autocorrelation, FFT of autocorrelation, FFT of input signal, and Power Spectral Density using `subplot`.

## PROCEDURE

* Refer Algorithms and write code for the experiment.
* Open SCILAB in System.
* Type your code in New Editor.
* Save the file.
* Execute the code.
* If any Error, correct it in code and execute again.
* Verify the generated waveform using Model Waveform.

---

## PROGRAM / CODE

```scilab
clc;
clear;
close;

t = 0:0.01:2*%pi;
x = 8 * cos(4*t);

subplot(3, 2, 1);
plot(t, x);
xgrid();
title("Input Cosine Signal");
xlabel("Time");
ylabel("Amplitude");

av = xcorr(x, x);
subplot(3, 2, 2);
plot(av);
xgrid();
title("Auto-Correlation");
xlabel("Lag");
ylabel("Correlation");

V = fft(av);
subplot(3, 2, 3);
plot(abs(V));
xgrid();
title("FFT of Auto-correlation");
xlabel("Frequency");
ylabel("Magnitude");

fw = fft(x);
subplot(3, 2, 4);
plot(abs(fw));
xgrid();
title("FFT of Input Signal");
xlabel("Frequency");
ylabel("Magnitude");

fw2 = (abs(fw)).^2;
subplot(3, 2, 5);
plot(fw2);
xgrid();
title("Power Spectral Density");
xlabel("Frequency");
ylabel("Power");
```

![Scilab Code Page 1](images/page_2.png)

![Scilab Code Page 2 and Record Evaluation](images/page_3.png)

---

## MODEL GRAPH / SCILAB OUTPUT

**Simulation Waveforms:**

![Input Cosine, Auto-Correlation, FFT, and PSD Output](images/page_1.png)

---

## RESULT

Thus, the auto-correlation and PSD of the given cosine signal were successfully obtained using Scilab.

![Result and Evaluation](images/page_3.png)
