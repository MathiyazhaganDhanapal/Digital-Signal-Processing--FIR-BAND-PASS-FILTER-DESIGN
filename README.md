# Digital-Signal-Processing--FIR-BAND-PASS-FILTER-DESIGN
## AIM:
To generate design of Band Pass FIR digital filter using Barlet Window.
## Software Required:
MAT LAB R2023a.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Band Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
~~~
clc; % clear screen
clear all; % clear workspace
close all; % close all figure windows

Wc1=input('enter the value of Wc1='); 
Wc2=input('enter the value of Wc2='); 
N=input('enter the value of N=');

alpha=(N-1)/2; 
eps=0.001;

% Band Pass Filter
n=0:1:N-1;
hd=(sin(Wc2*(n-alpha+eps)) - sin(Wc1*(n-alpha+eps)))./((n-alpha+eps)*pi);

% Hanning Window Sequence 
n=0:1:N-1; 
wh=0.5 - 0.5*cos((2*pi*n)/(N-1));

% Final impulse response
hn=hd.*wh; 

% Plot the Band Pass Filter with Hanning Window Technique
w=0:0.01:pi; 
h=freqz(hn,1,w);

plot(w/pi,abs(h),'b');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Band Pass FIR Filter using Hanning Window');
grid on;
~~~
## OUTPUT:

<img width="1601" height="871" alt="Screenshot 2026-03-29 100703" src="https://github.com/user-attachments/assets/7aeaf063-66cd-4b6d-9bae-fb40e09974ad" />

## RESULT:

Thus the design of Band pass FIR digital filter using Barlet waveforms were plotted and 
output was verified.
