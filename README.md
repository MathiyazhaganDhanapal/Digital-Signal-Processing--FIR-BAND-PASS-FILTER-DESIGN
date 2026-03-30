# Digital-Signal-Processing--FIR-BAND-STOP-FILTER-DESIGN
## AIM:
To generate design of Band Stop FIR digital filter using Barlet Window.
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

% Band stop Filter Coefficient 
n=0:1:N-1;  
hd=(sin(pi*(n-alpha+eps)) - sin((n-alpha+eps)*Wc2) + sin((n-alpha+eps)*Wc1))./(pi*(n-alpha+eps));

% Bartlett Window Sequence  
n=0:1:N-1;  
wh=1 - 2*abs(n-alpha)/(N-1);  

% Final impulse response
hn=hd.*wh;  

% Plot the Band stop Filter with Bartlett Window Technique 
w=0:0.01:pi;  
h=freqz(hn,1,w); 

plot(w/pi,abs(h),'b');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Band Stop FIR Filter using Bartlett Window');
grid on;
~~~
## OUTPUT:

<img width="1601" height="871" alt="Screenshot 2026-03-29 100703" src="https://github.com/user-attachments/assets/7aeaf063-66cd-4b6d-9bae-fb40e09974ad" />

## RESULT:

![WhatsApp Image 2026-03-30 at 2 36 27 PM](https://github.com/user-attachments/assets/ee173834-3a8a-4246-8f2b-15dc71f30d19)

