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

# OUTPUT: 
<img width="428" height="297" alt="image" src="https://github.com/user-attachments/assets/5d0a079d-e0bd-4df8-b962-2c202832b0f7" />

<img width="455" height="373" alt="image" src="https://github.com/user-attachments/assets/b4ae79ee-c417-434e-84c4-f757d6b3146f" />

# RESULT: 

Thus design of low pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 


# OUTPUT: 


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 


# OUTPUT: 


# RESULT: 
Thus design of BAND pass FIR digital filter using-Barlettr-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 


# OUTPUT: 


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.
