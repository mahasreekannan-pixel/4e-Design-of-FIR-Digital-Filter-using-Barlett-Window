# FIR-FILTER-DESIGN
# EXP 4e: Design-of-FIR-Digital-Filter-using-Barlett-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Barlett-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
<br>clc;
<br>close;
<br>M = input('Enter the Odd Filter Length = ');
<br>Wc = input('Enter the Digital Cut off frequency = ');
<br>alpha = (M-1)/2 // Center Value
<br>for n = 1:M
<br>    if (n == alpha+1) then
<br>        hd(n) = Wc/%pi;
<br>    else
<br>        hd(n) = sin(Wc*((n-1)-alpha)) / (((n-1)-alpha)*%pi);
<br>    end
<br>end
<br>// Bartlett Window
<br>for n = 1:M
<br>    W(n) = 1 - (2*abs((n-1)-(M-1)/2)/(M-1));
<br>end
<br>// Windowing filter coefficients
<br>h = hd.*W;
<br>disp(h, 'Filter Coefficients are')
<br>[hzm, fr] = frmag(h, 256);
<br>subplot(2,1,1)
<br>plot(2*fr, hzm)
<br>xlabel('Normalized Digital Frequency w');
<br>ylabel('Magnitude');
<br>title('Frequency Response of FIR LPF using Bartlett Window')
<br>hzm_dB = 20*log10(hzm);
<br>subplot(2,1,2);
<br>plot(2*fr, hzm_dB);
<br>xlabel('Normalized Digital Frequency W');
<br>ylabel('Magnitude in dB');
<br>title('Frequency Response of FIR LPF using Bartlett Window (dB)')

# Manual Calculation :
<img width="946" height="1568" alt="image" src="https://github.com/user-attachments/assets/bc55bf25-a757-4856-ae33-68aaf0328110" />
<img width="1099" height="1599" alt="image" src="https://github.com/user-attachments/assets/286dbbde-d054-4caa-9419-9c501e42f5be" />


# OUTPUT: 
<img width="428" height="297" alt="image" src="https://github.com/user-attachments/assets/5d0a079d-e0bd-4df8-b962-2c202832b0f7" />

<img width="455" height="373" alt="image" src="https://github.com/user-attachments/assets/b4ae79ee-c417-434e-84c4-f757d6b3146f" />

# RESULT: 

Thus design of low pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
<br>clc ; 
<br>close ; 
<br>M=input('Enter the Odd Filter Length ='); 
<br>Wc=input('Enter the Digital Cut off frequency ='); 
<br>alpha= (M -1)/2 // Center Value 
<br>for n = 1:M 
<br>if (n ==alpha+1) 
<br>hd(n) = 1-Wc/ %pi ; 
<br>else 
<br>hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
<br>end 
<br>end 
<br>// Bartlett Window 
<br>for n = 1:M 
<br>W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1)); 
<br>end 
<br>//Windowing filter coefficients 
<br>h = hd.*W; 
<br>disp(h,'Filter Coefficients are') 
<br>[hzm,fr]= frmag (h,256) ; 
<br>subplot(2 ,1 ,1) 
<br>plot(2*fr, hzm) 
<br>xlabel( ' Normalized Digital Frequency w'); 
<br>ylabel( 'Magnitude '); 
<br>title( ' Frequency Response of FIR HPF using Bartlett Window ') 
<br>hzm_dB = 20* log10 (hzm); 
<br>subplot (2 ,1 ,2); 
<br>plot(2*fr , hzm_dB); 
<br>xlabel( ' Normalized Digital Frequency W' ); 
<br>ylabel( 'Magnitude in dB'); 
<br>title('Frequency Response of FIR HPF using Bartlett Window');

# OUTPUT: 
<img width="437" height="371" alt="image" src="https://github.com/user-attachments/assets/9480a7fe-6528-4a54-bc09-e35d4d37c4ec" />


<img width="454" height="376" alt="image" src="https://github.com/user-attachments/assets/1ae86ba1-b5e5-4baf-91b4-9d64d1a8a12c" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1)); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Bartlett Window');
```
# OUTPUT: 
<img width="760" height="696" alt="image" src="https://github.com/user-attachments/assets/759dbdf7-f2a2-408b-97a2-9267d9dc1213" />
<img width="572" height="870" alt="image" src="https://github.com/user-attachments/assets/7e6873ca-c1ab-4949-8ac8-8bf3347d58d8" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Barlettr-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1)); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Bartlett Window');
```
# OUTPUT: 
<img width="757" height="687" alt="image" src="https://github.com/user-attachments/assets/eeab9ecc-22a1-4416-b69d-f87f126cda16" />
<img width="590" height="783" alt="image" src="https://github.com/user-attachments/assets/088d2405-3764-46a0-a98d-1b0a0d620372" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

