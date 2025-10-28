# RANDAR-RANGE-USING-SCILAB

## Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Scilab programming.

## Theory:
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:
<img width="371" height="431" alt="image" src="https://github.com/user-attachments/assets/570b1f56-7f9a-482b-827f-efc0529e6f5a" />

## Procedure
1. Refer to the Algorithm and write the Scilab code for the experiment.
2. Open Scilab on your system.
3. Create a New Editor File:
    Go to File → New → Script.
4. Type Your Code in the editor window.
5. Save the File with a suitable name (e.g., radar_range.sce).
6. Execute the Code:
7. Press F5 or click Execute → File with echo.
8. If Any Errors Occur: Review and correct the code.
9. Save and run it again until it executes successfully.


## CODE
```
clc;
clear;
clf;
Gt = 40;
Gr = 35;
l = 0.04;
s = 3;
Pm = 1e-10;
K = (4 * %pi)^3;
Pt = 0:0.5:100;
x = Pt .* Gt .* Gr .* l .* l .* s;
y = K * Pm;
z = x ./ y;
R = z.^(1/4);
subplot(3,1,1);
plot(Pt, R);
xlabel('Transmit Power (W)');
ylabel('Range (m)');
title('Range vs Transmit Power');
xgrid();
Pr = 0:10:1000;
Pt_fixed = 40;
x = Pt_fixed .* Gt .* Gr .* l .* l .* s;
y = K .* Pr;
z = x ./ y;
R1 = z.^(1/4);
subplot(3,1,2);
plot(Pr, R1);
xlabel('Received Power (W)');
ylabel('Range (m)');
title('Range vs Received Power');
xgrid();
G = 0:0.06:60;
Pm_fixed = 1e-10;
Pt_fixed = 40;
a = Pt_fixed .* G .* l .* l .* s;
b = K * Pm_fixed;
c = a ./ b;
R2 = c.^(1/4);
subplot(3,1,3);
plot(G, R2);
xlabel('Antenna Gain (G)');
ylabel('Range (m)');
title('Range vs Antenna Gain');
xgrid();
```

## OUTPUT
<img width="1662" height="991" alt="image" src="https://github.com/user-attachments/assets/13651c35-ad2b-4bd8-907e-1c4b71d3a657" />

## MANUAL CALCULATION
<img width="940" height="646" alt="image" src="https://github.com/user-attachments/assets/ce6f53d2-9238-4355-b9ba-1a8ce0b429cb" />

## RESULT
Thus, the maximum range of a radar system using the Radar Range Equation is verified through a Scilab program.
