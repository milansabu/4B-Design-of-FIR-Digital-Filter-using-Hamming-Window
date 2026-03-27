# FIR-FILTER-DESIGN
# EXP 4 b: Design-of-FIR-Digital-Filter-using-Hamming-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hamming-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; 
else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Hamming Window 
for n = 1:M 
W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR LPF using Hamming Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Hamming Window');
```
# CALCULATION:
<img width="1600" height="442" alt="image" src="https://github.com/user-attachments/assets/122e42c2-ad9f-465c-b509-bb8181c581fb" />
<img width="480" height="425" alt="image" src="https://github.com/user-attachments/assets/ddfb08d7-a579-4f0f-8a83-04e479e8abba" />

# OUTPUT: 
<img width="762" height="723" alt="image" src="https://github.com/user-attachments/assets/4a822d7b-7f12-4620-9cc7-25607be8d2e0" />

<img width="1600" height="919" alt="image" src="https://github.com/user-attachments/assets/cb986153-6899-4a57-914d-1f3c0cec02b1" />

# RESULT: 

Thus design of low pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-Wc/ %pi ; 
else 
hd(n) =-sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Hamming Window 
for n = 1:M 
W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Hamming Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Hamming Window');
```

# CALCULATION:
<img width="1600" height="911" alt="image" src="https://github.com/user-attachments/assets/eda268a8-d529-4a5e-98a3-7aa4a8197729" />
<img width="1600" height="417" alt="image" src="https://github.com/user-attachments/assets/10219979-0c21-46fb-a6f7-53a957054094" />


# OUTPUT: 
<img width="449" height="474" alt="image" src="https://github.com/user-attachments/assets/76afc697-4766-411d-bb3f-772e03ba71b3" />

<img width="769" height="727" alt="image" src="https://github.com/user-attachments/assets/632da54a-9e65-46f9-83ae-22b8c1c658b0" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

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
// Hamming Window 
for n = 1:M 
W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Hamming Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Hamming Window');
```
# CALCULATION:
<img width="570" height="466" alt="image" src="https://github.com/user-attachments/assets/afe9b37e-ca41-4e6e-b1f4-e3c74eae29cc" />

<img width="1600" height="839" alt="image" src="https://github.com/user-attachments/assets/d520e48e-1a38-499a-b98c-5caa20af4b35" />

# OUTPUT: 
<img width="761" height="724" alt="image" src="https://github.com/user-attachments/assets/11c938f0-c23c-45de-83fd-7f9d35ea340b" />

<img width="1600" height="497" alt="image" src="https://github.com/user-attachments/assets/326c1f03-e4ab-4e73-b469-288613c87674" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.

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
hd(n) =1-((Wc2-Wc1)/%pi) ; 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Hamming Window 
for n = 1:M 
W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Hamming Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Hamming Window');
```

# CALCULATION:

<img width="548" height="507" alt="image" src="https://github.com/user-attachments/assets/437c77be-db32-4f46-bd24-fad4bb2bc5c2" />

# OUTPUT: 
<img width="758" height="719" alt="image" src="https://github.com/user-attachments/assets/8e157604-f273-4c0e-95b2-8fc3fca952df" />
<img width="1600" height="1210" alt="image" src="https://github.com/user-attachments/assets/971dbd54-9d80-4b8a-8851-d2dbdb3ac5e8" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hamming-Window waveforms were plotted and output was verified.
