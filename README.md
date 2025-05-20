## Ideal-Sampling
### Santhosh J
### 212223060248
### 01/03/25
## Aim
To study and analyze Ideal Sampling (Impulse Sampling), where a continuous-time signal is sampled using an impulse train, and observe its effects in both time and frequency domains. The experiment aims to verify the sampling theorem, analyze spectral characteristics, and understand signal reconstruction.

## Tools Required
Python: A versatile programming language used for scientific computing and signal processing. NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations. Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.

## Program
```
# Impulse Sampling
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample

# Define parameters
fs = 100  # Sampling frequency
f = 5  # Signal frequency
t = np.arange(0, 1, 1/fs)  # Time vector

# Generate continuous signal
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Perform sampling
signal_sampled = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Reconstruction of signal
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

```
## Output Waveform
![Screenshot 2025-05-20 194416](https://github.com/user-attachments/assets/606084a3-f0c7-4819-b75f-3fdc1bcb240e)



## Result
The result of ideal sampling is a discrete-time signal that retains all the information of the original continuous-time signal is obtained and output is verified.
