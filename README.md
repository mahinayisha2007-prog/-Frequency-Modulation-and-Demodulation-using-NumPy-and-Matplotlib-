# -Frequency-Modulation-and-Demodulation-using-NumPy-and-Matplotlib-

__Aim:__

To implement and analyze frequency modulation (FM) using Python's NumPy and Matplotlib libraries.

__Apparatus Required:__ 

1. Software: Python with NumPy and Matplotlib libraries
   
2. Hardware: Personal Computer

 
__Theory:__

Frequency Modulation (FM) is a method of transmitting information over a carrier wave by varying its 
frequency in accordance with the amplitude of the input signal (message signal). The frequency of the carrier 
wave is varied according to the instantaneous amplitude of the message signal.

__Algorithm:__

1. Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and 
   frequency deviation.
   
2. Generate Time Axis: Create a time vector for the signal duration.
    
3. Generate Message Signal: Define the message signal as a cosine wave.
    
4. Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
    
5. Generate FM Signal: Apply the FM modulation formula to obtain the modulated signal.
 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Programme:__
```
import numpy as np
import matplotlib.pyplot as plt

fs = 50000
t = np.arange(0, 0.01, 1/fs)

m = np.sin(2*np.pi*200*t)        # message
fc = 5000                        # carrier
kf = 50                          # frequency sensitivity

integral_m = np.cumsum(m) / fs

s_fm = np.cos(2*np.pi*fc*t + kf * integral_m)

plt.figure(figsize=(8,6))

plt.subplot(3,1,1)
plt.plot(t[:1000], m[:1000])
plt.title("Message Signal")

plt.subplot(3,1,2)
plt.plot(t[:1000], np.cos(2*np.pi*fc*t)[:1000])
plt.title("Carrier Signal")

plt.subplot(3,1,3)
plt.plot(t[:1000], s_fm[:1000])
plt.title("FM Signal")

plt.tight_layout()
plt.show()
```
__Output:__
![WhatsApp Image 2025-11-21 at 16 15 41_99771423](https://github.com/user-attachments/assets/d56e6af1-2474-4256-93f4-0993da56d3ff)

<img width="1280" height="827" alt="517232885-7478b57f-373b-45d0-bb83-9a4e822dcb51" src="https://github.com/user-attachments/assets/7818a3fe-179d-49ae-af90-d81ed5f23ac1" />

__Result:__

Thus the FM modulation and demoulation using python wsa succesfully executed and its output was verified.


