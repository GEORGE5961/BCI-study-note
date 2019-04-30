# BCI Study Note
# Lecture 1
## Lecture 1.1 What’s BCI?
### General def
Take a bio signal from a person -> BCI -> State prediction

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/1.png" width="50%">

### 3 BCI  subtypes
* Active BCI
	* For controlling an application
* Reactive BCI
	* In reaction to external stimulation
* Passive BCI
	* Arbitrary brain activity

### Brain signals
* Electroencephalogram (EEG)
* Functional Near-Infrared  Spectroscopy (fNIRS)
	* Using blood oxygen level in the brain
	* Not for use (so changing signals) 
* Invasive brain signals
	* For monkeys
* Room-sized sensors
	* MEG
	* fMRI

### Non-brain signals
* Motion capture, Eye tracking
* EMG, ECG, EOG
* System state, environmental state

### What can we estimate?
* Aspect of cognitive state
	* Tonic state: degree of  relaxation…
	* Phasic state: switching attention…
	* Even-related state: surprised…

## Lecture 1.2  Application areas
* Unhealthy population
	* Speller programs
	* Prosthetic control, home automation
* Healthy population
	* Brake intent (save a couple of meters), line-change intent
	* Operator monitor 
	* Lie detection
	* Entertainment 
	* Personal health
	* Social application 
	* Neuroscience

## Lecture 1.3  Scientific challenge

* Related areas
	* Signal processing, ML,  computational intelligence
	* Neuroscience, cognitive science

* Why BCI is hard?
	* People vary in brains
	* Relevant map differs across individuals
	* Sensor’s location
	* Brain is dynamic 
	* Noisy data
	* Specific phenomenon is hard to measure

## Lecture 1.4 Available tools & a demo
* Cross-platform tool 
	* Matlab / C++ / Python
* Record audio / mouse of PC /  EEG

# Lecture 2
## Lecture 2.1 Underlying brain process
* Large-scale brain process
	* When would 50000 neurons fire near-synchronously?
		* An external event triggers a cascade of related neural processes (e.g., in perception)
		*  An internal event triggers a cascade of related neural processes (e.g., in perception)
		* Neural populations enters a synchronized steady-state firing pattern (e.g., idle oscillations)
	* Two major BCI-detectable EEG/MEG phenomenon
		*  Event-Related Potentials (ERPs)
		*  Oscillations Processes

## Lecture 2.2 Spatial Characteristics
* Functional mapping
	* For most regions, morel or less well know functional associations exist

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/2.png" width="50%">


* Volume conduction
	* Neural activity is conducted through the brain volume to the scalp and sensors by Volume Conduction
	* Volume conduction is linear
	* Each sensor measures a weighted sum of each neural’s activity

         <img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/3.png" width="50%">

* Measurement sites

    <img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/4.png" width="50%">
    
* Equivalent Dipole model
	* Localize the source

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/5.png" width="50%">
	
	* Problems
		* Require knowledge about sensor locations
		* Require assumptions about  conductivities of scalp, skull, cerebrospinal,  brain issue
		* …
* Distributed Source model
	* Many methods
		* sLORETA
		* Beamforming
		* Sparse Bayesian Learning
	* Prone to finding only locally optimal solutions

     <img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/6.png" width="50%">

      <img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/7.png" width="50%">

## Lecture 2.3 Temporal characteristics
* Neural vs Scalp activity

	<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/8.png" width="50%">

* Oscillatory process
	* EEG is full of oscillatory such as alpha rhythm

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/9.png" width="50%">
	
	* Rhythms
		* delta (0-4 Hz)
		* theta (4-7 Hz)
		* alpha (8-13 Hz)
		* beta (12-30 Hz)
		* gamma (25-100 Hz)

## Lecture 2.4 Complex EEG phenomena
* EEG source separated by ICA

	<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/10.png" width="50%">

## Lecture 2.5 Non-brain artifacts 
* Internally generated
	* neck, face and eye muscle, eye dipoles, heart activity
* Externally generated
	* 50/60 Hz line noise, EM spikes from equipment
* Sensor-related
	* DC offset drifts, cable sway, thermal noise, quantization noise

	<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/11.png" width="50%">

	<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/12.png" width="50%">

## Lecture 2.6 Sensing and Acquisition

# Lecture 3
## Lecture 3.1 The Role of Signal Processing

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/13.png" width="50%">


<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/14.png" width="50%">

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/15.png" width="50%">

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/16.png" width="50%">

## Lecture 3.2 Major Filter Classes

* Static filters
	* Signal squaring

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/17.png" width="50%">

	* Logarithm

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/18.png" width="50%">

* Spatial filters 
	* Most spatial filters are linear
	* Y(n)= **M**X(n) for some matrix **M**

     <img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/19.png" width="50%">

     <img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/20.png" width="50%">
    
* Temporal filters
	* Transform a multi-channel signal X(n) such that each channel yi(n) in Y(n) depends only on the channel xi(n)
	* Example
	
		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/21.png" width="50%">
	
* Sepectral filters
	* Spectrum of a signal: a representation of the signal as a sum of  N sinusoidal components

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/22.png" width="50%">

	* A equivalent (more common) representation is the Fourier Series representation

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/23.png" width="50%">

	* Examples
		* High-pass
		* Low-pass

          <img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/24.png" width="50%">

	* A key spectral filter

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/25.png" width="50%">

		* Filter implementation
	
			<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/26.png" width="50%">
		
		* FIR filter implementation in MATLAB

			<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/27.png" width="50%">

##  Lecture 3.3 A simple neurofeedback BCI

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/28.png" width="50%">

## Lecture 3.4 Prediction Function Notion
* Classification

 <img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/29.png" width="50%">
 
* pipeline

	<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/30.png" width="50%">

* neurofeedback

	<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/31.png" width="50%">

# Lecture 4
## Lecture 4.1 Adaptivity in BCIs

- Prior knowledge
	- Anatomical atlases
		- Talairach
		- LONI

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/32.png" width="50%">
	
	- Functional atlases (if available)
	- Timing infomation
		- Neural latencies
		- reaction times
	- Frequency bands of oscillatory processes
		- alpha 
		- beta
		- theta

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/33.png" width="50%">

* Calibration data (training data )
	* To calculate optimal params of a BCI

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/34.png" width="50%">

## Lecture 4.2 Machine learning
* Feature extraction
	* Caveat — off-the-shelf machine learning methods doesn’t work well when applied to raw segments of the calibration recording
		* Too much dimension — too much params to fit
		* Too complex structure — too much modeling freedom 

		<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/35.png" width="50%">

## Lecture 4.3 Concrete Case Study

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/36.png" width="50%">

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/37.png" width="50%">

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/38.png" width="50%">

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/39.png" width="50%">

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/40.png" width="50%">

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/41.png" width="50%">

## Lecture 4.4 Performance Evaluation
* Time series data like EEG
	* Prefer block-wise cross-validation over randomized 

# Lecture 5

## Lecture 5.1 Task

<img src="https://github.com/GEORGE5961/BCI-study-note/blob/master/img/42.png" width="50%">
