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

```
# Output Waveform
# PSK

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/2d71c13a-92dc-40df-a620-41e6021e0f51" />

# QPSK

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/d51f418f-42e3-4b78-b9dd-225a8fcc2d63" />


# Results
Thus PSK and QPSK were performed and the waveform is verified using Google Colab.
