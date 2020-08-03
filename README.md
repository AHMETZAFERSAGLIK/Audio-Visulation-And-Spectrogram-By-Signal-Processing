# Audio-Visulation-And-Spectrogram-By-Signal-Processing


1 - Audio Visualization 
In this part  you will use DFT for audio visualization. Steps are given 
below for a basic audio visualizer: 
 Select the visualization renewal rate (e.g. 10 FPS). Since you know the sample 
rate in Hertz (44100 in the given le.), you can select data from the audio array 
which is matching with renewal time. For example, to visualize at 10 FPS, each 
visualization interval comes from 4410 values in sampled audio matrix. Pad the 
audio matrix with zeroes if necessary. 
 For each visualization interval; 
{ Find FFT of that interval using built-in functions. Since it's in exponential 
form, it will give an array of complex numbers. Find the magnitude of each 
value. 
{ The transformed values have a great range because of the outliers. For a 
better representation, logarithm operation 10  log10(xft +c) is used for each 
value. Here c can be a small number to avoid log10(0). 
1

BLG354E Homework-4 
{ Since the obtained transformation is mirrored (see conjugate symmetry prop- 
erty) you may use: 
 The rst half of the array 
(http://web.itu.edu.tr/sahinyu/HallOfTheMountainKingN2.mp4, 
https://web.itu.edu.tr/sahinyu/SilentKnight.mp4) 
 Shifted version of the array using tshift function 
(http://web.itu.edu.tr/sahinyu/HallOfTheMountainKingFFTShift. 
mp4) 
 After obtaining transforms for all visualization intervals, you can plot the trans- 
forms using matplotlib's \bar" function and write the results to a video le. An 
example video le writing operation using OpenCV is given below. 

Create an audio visualization of the given song. If the result mp4 le is larger than 20 
MB, you can share the le with me via Dropbox. 
Note: To speed-up the gure rendering, you can use 'plot' function instead of bar 
function. However, do not forget to limit the y-axis with constant values. If you use 
plot function, a frame from your solution will be like as given below. 
Figure 1: An example output when plot is used. 

2 The Spectrogram 
In this part you will work on a part of Aphex Twin's famous song 
 The artist hid a face in the 
song which can be seen by creating a spectrogram and analyzing it in log scale. To do 
this,
 Normalize the signal according to its max value as you've done in the previous 
homework. 
 Dene two parameters: 
{ Window Size: Size of the rectangular window 
{ Step: It is unnecessary to calculate the FFTs for every data point. Thus, 
starting from 0th data point, you should decide on next data points according 
to step value. 
3

BLG354E Homework-4 
 Fill the spectrogram matrix using absoulte FFTs of the windowed data. As in the 
previous part, you can also work on the rst half of FFT. 
 Use 10  log10(x + c) to smooth the data for a better representation. 
 Use pcolormesh function of matplotlib to obtain a visual from the data. The artist 
hid the face into log scale. Thus, you should select 'y scale' as 'symlog'. 
If everything goes well, you will obtain the face given in Figure 2. 

