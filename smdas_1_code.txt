% Step Response of RC Circuit
clc; clear all; close all;
t=(0:0.01:15); V0=0; C=1; R=1; Tou=R*C; Vs=1;
vC=Vs+((V0-Vs)*exp(-t/Tou));
iR=Vs/R*exp(-t/Tou);
subplot(211); plot(t,vC,'red', t, iR,'blue'); grid on;
xlabel('Time');ylabel('Capacitive Voltage & Capacitve Current');
title ('RC Step Response - Capacitive Voltage and Capacitive Current')
legend ('Capacitive Voltage','Capacitive Current')
vR=R*iR;
subplot(212); plot(t,vR,'black'); grid on;
xlabel('Time');ylabel('Resistive Voltage Amplitude');
title ('RC Step Response - Resistive Voltage')
legend ('Resistive Voltage')
% % RC Step Responses with Different Time Constants
t=(0:0.01:12); V0=0; Vs=1;
C=1; RA=0.5; RB=1; RC=2;
TA=RA*C; vA=Vs+((V0-Vs)*exp(-t/TA)); 
TB=RB*C; vB=Vs+((V0-Vs)*exp(-t/TB)); 
TC=RC*C; vC=Vs+((V0-Vs)*exp(-t/TC)); 
plot(t,vA,'black', t,vB,'blue',t,vC,'red');
legend ('Smallest Tou - FASTEST','Moderate Tou','Highest Tou - SLOWEST')
xlabel('Time');ylabel('Voltage Output for Step I/P');
title('RC Step I/P - Voltage Responses with Different Time Constants & System Fastness');
grid on;
%%% iA=I0*exp(-t/TA); iB=I0*exp(-t/TB); iC=I0*exp(-t/TC);