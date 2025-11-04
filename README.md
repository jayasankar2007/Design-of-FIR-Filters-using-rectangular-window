# Design-of-FIR-Filters-using-rectangular-window
#          DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
// DESIGN OF LOW PASS FIR FILTER USING RECTANGULAR WINDOW

clc;
clear;
close;

// Filter specifications
N = 21;          // Filter length
fc = 0.12;       // Normalized cutoff frequency (0 < fc < 0.5)
M = N - 1;
n = 0:M;

// Ideal impulse response (sinc function)
hd = 2 * fc * sinc(2 * fc * (n - M/2));

// Rectangular window
w = ones(1, N);

// FIR filter coefficients
h = hd .* w;

// Frequency response
[H, f] = frmag(h, 1024);   // magnitude response

// ---- Plot impulse response (use plot2d3 instead of stem) ----
figure(1);
plot2d3(n, h);
title('Impulse Response of FIR Low Pass Filter (Rectangular Window)');
xlabel('n');
ylabel('h[n]');
xgrid();

// ---- Plot magnitude response ----
figure(2);
plot(f, abs(H));
title('Magnitude Response');
xlabel('Normalized Frequency');
ylabel('|H(f)|');
xgrid();

// ---- Display filter coefficients ----
disp("Filter Coefficients (h[n]):");
disp(h');

disp("Filter length (N): " + string(N));
disp("Cutoff frequency (fc): " + string(fc));
disp("Window used: Rectangular");

# OUTPUT
<img width="300" height="498" alt="image" src="https://github.com/user-attachments/assets/274f58bc-c9ef-48e5-aee9-d87f97b24397" />
<img width="362" height="498" alt="image" src="https://github.com/user-attachments/assets/223ada08-c04c-4470-8e72-29968734cb47" />
<img width="358" height="432" alt="image" src="https://github.com/user-attachments/assets/8da9d334-c3bb-42d0-863c-5e9fa7996946" />


# RESULT
Design of low pass FIR digital filter using SCILAB was generated.
