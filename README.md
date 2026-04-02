# DSB--SC-MODULATION-AND-DEMODULATION-USING-PYTHON

__AIM__:

To generate a Double Sideband Suppressed Carrier (DSB-SC) signal in Python (Google Colab), transmit it (optionally add noise), and recover the message using coherent (synchronous) demodulation with a low-pass filter. Observe time and frequency domain waveforms and measure demodulation performance

__APPARATUS REQUIRED__:

Google Colab (or any Python environment)

Python libraries: numpy, matplotlib, scipy (scipy.signal)

__Theory__:

DSB-SC signal: s(t) = m(t) · cos(2πf_c t)
Coherent demodulation: multiply received s(t) by a synchronized carrier cos(2πf_c t) then low-pass filter (LPF) to remove double-frequency components:

r(t) = s(t)·cos(2πf_c t) = m(t)·cos²(2πf_c t) = 0.5 m(t) + 0.5 m(t)·cos(4πf_c t)
LPF extracts 0.5·m(t) → scale by 2 to recover m(t).

__Procedure__:

1) Import libraries and set parameters
2) Define message and carrier signals
3) Generate DSB-SC signal (modulation)
4) View spectra (FFT) of message and DSB-SC
5) (Optional) Add noise
6) Coherent demodulation (multiply by synchronized carrier)
7) Low-pass filter to recover message

   __Program__:

  ```
  import numpy as up 
  import matplotlib. pyplot as plt
  Am = 3.7
  fm = 166
  fs = 16600
  
  t=np.arange(0,2/fm,1/fs)
  m=Am*np.cos (2*np. pi*fm*t)
  
  plt = Subplot (3,1,1)
  plt.plot(t,m)
  Ac = 7.4
  fc = 1660
  C = Ac*np. Cos (2*np. pi*fc*t)
  plt. Subplot (3.1, 2)
  plt.plot(t,c)
  
  S1 = (Ac+m)*np.cos(2*np.pi*fc*t)
  S2 = (Ac - m)*np.cos(2* np.pi*fc*t)
  
  S = S1-S2
  plt.Subplot(3,1,3)
  plt.plot(t,s)

  ```

  
   __Tabulation__:

![WhatsApp Image 2026-04-02 at 2 03 57 PM](https://github.com/user-attachments/assets/172616ef-06c9-4383-a5d0-cb45df05cfe4)


   __Output__:

![WhatsApp Image 2026-04-02 at 2 03 26 PM](https://github.com/user-attachments/assets/7bc0b4e8-8a9c-41fe-8c3e-d14c39b0f810)


   __Result__:

Tjus, the DSB - SC AM modulation is generated using python 
