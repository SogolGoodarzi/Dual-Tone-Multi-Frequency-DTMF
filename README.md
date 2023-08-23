# Dual-Tone-Multi-Frequency-DTMF

#### A brief introduction to DTMF:
<p align="justify"> DTMFs are binary tones (two tone signals with different frequencies) that are generated when dialing numbers are pressed and sent to the telecommunication center. Since sound cannot produce these tones, one of the tones is created through a high frequency group of tones and the other tone is produced from a low frequency group. The reason for combining two frequencies with this combination is that the production frequency cannot be produced by the human voice so as not to cause interference in exchanging information. </p>

<p align="justify"> DTMFs generally consist of 16 types of frequencies that represent numbers and telecommunication signs (* and #) as well as letters A-D. For example, key 1 produces a low frequency of 697 Hz and a high frequency of 1209 Hz. </p>

![image](https://github.com/SogolGoodarzi/Dual-Tone-Multi-Frequency-DTMF/assets/125180530/37a333be-ce8f-4b76-a7f1-011e52029f6c)

<p align="justify"> The main application of DTMF tones is in telecommunications and is known as a telecommunication signaling system that is carried out using the audio frequency band through telephone lines between telephone equipment and other switching centers. But these codes can be used to communicate between electronic circuits and devices such as computers, mobile phones, and so on. According to the type of transmitter and receiver, the designers specify how to produce these codes (hardware, i.e. using ICs or using software such as MATLAB). </p>

<p align="justify"> There are 16 DTMF sounds in the dtmf folder. It is expected that there are two peaks in the Fourier transform of each of these sounds, one of which represents the low frequency and the other represents the high frequency of the sound. Suppose that the noise in the sounds does not cause the displacement of the peak of the sound conversion. Therefore, by using fft and dominant frequency detection, the type of sound can be recognized. </p>

* <p align="justify"> According to the frequency values ​​shown in the previous figure, write a function with the format keyboard = dtmf(y,fs) in such a way that it receives the audio signal y and its sampling frequency and then determines the dominant frequency y with fft and finally recognizes this audio signal is created by pressing which key. Save the pressed key character in the keyboard variable. You can use the given 16 audio files to check the function and make sure that the function recognizes the character correctly. </p>

<p align="justify"> Since the Fourier transform of each key contains two peaks, to distinguish them, we first divide the Fourier transform into two parts to find the frequency peak for the rows and the frequency peak for the columns. In order to find the corresponding frequency of these peaks, corresponding to dividing the signal, we have divided the range of frequencies into two parts. If you pay close attention, the frequency of the keyboard rows is between 600 and 1000 Hz, and the frequency of the columns is between 1100 and 1700 Hz. So we do the division based on these two ranges. After obtaining two peaks in the Fourier transform values, we define the appropriate frequency ranges for each of the keys and compare them with the written conditions and find the row and column numbers. </p>

To check the correctness of the commands, we try the function for one of the keys:

![image](https://github.com/SogolGoodarzi/Dual-Tone-Multi-Frequency-DTMF/assets/125180530/11a78a25-ef55-4eec-b6b0-eb0d17e4d422)

* <p align="justify"> In this section, write a code to find the 8-digit phone number of the audio file "phone_number.wav" using the dtmf function. </p>

<p align="justify"> To get an 8-digit phone number, we divide the given audio signal into 8 equal parts. The number of signal samples is 22400, which divided by 8 gives the number of 2800. So we conclude that we have 2800 samples for each key. We give these samples separately to the function written in the previous part and extract each digit of the phone number. In fact, in a loop, we separate these samples and call the function for every 8 digits. The output is as follows. </p>

![image](https://github.com/SogolGoodarzi/Dual-Tone-Multi-Frequency-DTMF/assets/125180530/a933e014-66a8-4e9c-8fbd-b98ce6b33ad6)
