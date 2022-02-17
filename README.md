# CardioScripts
Scripts for calculations of cardiac data such as MEA results and calcium sparks.

#FLUOMAGIC

Script, that uses scipy.signal.find_peaks function to find peaks from curve, obtained from calcium imaging via confocal. It uses bessel filtration:

b, a = scipy.signal.bessel(2, 0.1)
filtered = scipy.signal.filtfilt(b, a, y)

run(folder=string) function are used for automatic calculation of files from path specified path (folder).

It also can be used for saving of filtered data, peak indexes and peak heights (by main2 function). 


#FLUOMAGIC for peak analysis
Version of FLUOMAGIC for detecting peak decay (time from peak highest point to peak end) and time-to-peak (ttp as time from peak start to highest point of the peak).
It's made by areafinder(dataname=string) function, that returns ttps (time-to-peak values) and decays (decay values) lists for dataname file variable. 
It also can be configured for relative peak area as the area of the triangle formed by end, start and highest point of the peak.

#afmscript

Usefull tool for cardiac cell contraction data obtained by AFM. 
main (name, treshold, prom, hint, mint, qs, qr)
name - filename or path
treshold, prom - threshold and prominence values for scipy.signal.find_peaks.
mint and hint is start and end points of data in time (seconds) that should be analysed.  
qs - region that should be escaped for R or S peak finder. 
qr - the size of the region (time indexes) where we expect to find the end or beginning of the peak

#afmscript_doubleEBs

Modification of AFM script for double-EBS model. That accuratly same with afmscript, but find peaks using data flip in Y-direction.

#newMEAscrptAuto
Script, optimised for calculation of MEA-60 experimetal data obtained with HL-1 cells. 

#newMEAscrptAuto, #afmscript and #afmscript_doubleEBs provides information about RS amplitude, bpm, timepoints of R/S events, prominences of R and S peaks.  

#MEAscript v 2.0
New version of MEAScript with all QRST detection options.
