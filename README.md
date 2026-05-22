# PSK
# Aim
Write a simple Python program for the modulation and demodulation of PSK and QPSK.
# Tools required
# Program
```
import numpy as np
import matplotlib.pyplot as plt

# Input bits
data = [1, 0, 1, 1, 0, 1]

# Parameters
fs = 1000
fc = 5
t = np.arange(0, 1, 1/fs)

# Message signal
message = np.repeat(data, len(t))

# Time axis
time = np.arange(len(message)) / fs

# Carrier signal
carrier = np.sin(2 * np.pi * fc * time)

# ASK Modulation
ask = message * carrier

# Demodulation
demod = np.abs(ask)
reconstructed = (demod > 0.5).astype(int)

# Plot
plt.figure(figsize=(10,6))

plt.subplot(4,1,1)
plt.plot(time, message)
plt.title("Message Signal")

plt.subplot(4,1,2)
plt.plot(time, carrier)
plt.title("Carrier Signal")

plt.subplot(4,1,3)
plt.plot(time, ask)
plt.title("ASK Signal")

plt.subplot(4,1,4)
plt.plot(time, reconstructed)
plt.title("Demodulated Signal")

plt.tight_layout()
plt.show()
Attach the program
```
# Output Waveform
```
Attach the output waveform
```
# Results
```
Attach the output waveform
```
# Hardware experiment output waveform.
