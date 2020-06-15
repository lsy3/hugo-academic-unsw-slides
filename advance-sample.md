---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "EMBC2020 CKF+Distance"
summary: ""
authors: []
tags: []
categories: []
date: 2020-06-08T11:44:57+10:00
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: white
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
  # Choose to display slide number. true/false (default).
  slide_number: true
  # Vertical centering of slides. true (default) / false
  vert_center: false
---

<link rel="stylesheet" href="unsw-theme/reveal_custom.css">
<div class="footer">
	<p>Copyright ©2020 All Rights Reserved</p>
</div>
<style>
	.vert-align-center {
		top: 25%;
	}
</style>

{{< slide background-color="#FFFFFF" class="vert-align-center" >}}

<div class="multi-column">
<div class="col1">
	<img src="unsw-theme/unsw-portrait.png" alt="UNSW" width="150px" style="position: relative; top: 8%; background-color: #ffe600; padding: 20px;">
</div>

<div class="col4" style="padding: 0px 20px;">

# Estimating Lower Limb Kinematics using Distance Measurements with a Reduced Wearable Inertial Sensor Count

**Luke Wicent Sy**, Nigel Lovell, Stephen Redmond

</div>

</div>

{{% speaker_note %}}

	Good day to the audience!
	I on behalf of my co-authors will be presenting about our paper entitled.

{{% /speaker_note %}}

---

## Gait Analysis

<div class="multi-column">
	<div class="col1">
		<img src="figs/app-osteoarthritis.jpg" alt="Osteoarthritis" height="200px" width="100%" style="object-fit: contain; object-position: 50% 50%">
		<p style="text-align: center">Osteoarthritis</p>
		<img src="figs/app-cp.jpg" alt="Cerebral Palsy Surgery" height="200px" width="100%" style="object-fit: contain; object-position: 50% 50%">
		<p style="text-align: center">Cerebral Palsy Surgery</p>
	</div>
	<div class="col1">
		<img src="figs/app-parkinsons.jpg" alt="Parkinson's Disease" height="200px" width="100%" style="object-fit: contain; object-position: 50% 50%">
		<p style="text-align: center">Parkinson's Disease</p>
		<img src="figs/app-perfimprov.jpg" alt="Perform. Improvement" height="200px" width="100%" style="object-fit: contain; object-position: 50% 50%">
		<p style="text-align: center">Perform. Improvement</p>
	</div>
	<div class="col1">
		<img src="figs/app-fall.png" alt="Fall risk assessment" height="200px" width="100%" style="object-fit: contain; object-position: 50% 50%">
		<p style="text-align: center">Fall risk assessment</p>
		<img src="figs/app-gaitfeedback.png" alt="Real Time Feedback" height="200px" width="100%" style="object-fit: contain; object-position: 50% 50%">
		<p style="text-align: center">Real Time Feedback</p>
	</div>
</div>

{{% speaker_note %}}
People has long been fascinated by the study of human motion, also known as gait analysis.
Gait analysis has been used in a wide range of clinical application.

Specific examples:
- GA changes or reinforces surgical decision making for children with CP. 
Gait analysis helps the doctor understand existing gait deviations in cerebral palsy patients.
- In sports, it is used for performance improvement and injury
- In geriatrics, it can help assess fall risk. Research studies have shown some gait paremeters
are good indicator of fall risk. 


- Hausdor etal has shown that stride time variability, an example of a parameter measured for gait analysis, is a good indicator of fall risk.
- In rheumatology, it can help diagnose osteoarthritis
- In neurology, it can help diagnosis Parkinson's disease, understand gait deviations, and then inform therapy.
- In sports, it is used for performance improvement and injury prevention.
- Last, gait analysis is integral to gait assistive devices. These devices can provide real time feedback (e.g. haptics) which can help correct

{{% /speaker_note %}}

---

## Motion Capture Systems

<div class="multi-column">
	<div class="col1">		
		<img src="figs/hmcs-vicon.jpg" alt="Camera based" height="250px" align="center" style="object-fit: contain; object-position: 50% 50%">
		<h4 style="text-align: center">Camera based</h4>
		<p class="center">Very accurate but limited to a small space</p>
	</div>
	<div class="col1" >
		<span class="fragment" data-fragment-index="1" style="position: absolute; top:0; left:0;">
			<img src="figs/imu.png" alt="IMU based OSPS" height="250px" width="100%" align="center" style="object-fit: contain; object-position: 50% 50%">
			<h4 style="text-align: center">Inertial Measurement Unit (IMU)</h4>
			<p class="center">Miniaturization. Track position and orientation (albeit with drift).</p>
		</span>
		<span class="fragment" data-fragment-index="2" style="position: absolute; top:0; left:0; background: white;">
			<img src="figs/hmcs-xsens.jpg" alt="IMU based OSPS" height="250px" width="100%" align="center" style="object-fit: contain; object-position: 50% 50%">
			<h4 style="text-align: center">IMU based (one sensor per seg)</h4>
			<p class="center">Can capture almost everywhere. Can be conspicuous for everyday use</p>
		</span>
	</div>
	<div class="col1" >
		<img src="figs/zozo-small.jpg" alt="Wearable based sparse" class="fragment" data-fragment-index="3" height="250px" width="150px" style="object-fit: contain; object-position: 50% 50%">
		<img src="figs/hmcs-sparse.png" alt="Wearable based sparse" class="fragment" data-fragment-index="3" height="250px" width="150px" style="object-fit: contain; object-position: 50% 50%">
		<span style="position:absolute; top: 250px; left: 10%;" class="fragment" data-fragment-index="3">
			<h4 style="text-align: center" >Wearable based</h4>
			<p>More comfortable</p>
			<ul>
				<li>Soft stretch sensors</li>
				<li>More & smaller IMUs</li>
				<li>Sparse sensors</li>
			</ul>
		</span>
		<span style="position:absolute; top: 250px; left: 10%;" class="fragment" data-fragment-index="4">
			<h4 style="text-align: center" >Wearable based</h4>
			<p>More comfortable</p>
			<ul>
				<li>Soft stretch sensors</li>
				<li>More & smaller IMUs</li>
				<li style="background-color: rgba(255,230,0,1)">Sparse sensors</li>
			</ul>
		</span>
	</div>
</div>

{{% speaker_note %}}
A very integral technology to do gait analysis are MCS.
MCS is not just used in clinical applications but also in animation, robotics, and VR.
Motion capture is the tracking of the human body, where the system estimates the joint positions and orientations of body segments.

- Camera based - current gold standard, can reach mm accuracy, but limited to the room.
- There are a lot of potential for capturing motion in subject's natural environment, 
- Including better understand of disorder evolution OR early intervention. Goal: find tech to enable remote GA.
- Recent trend is miniaturation of IMUs. With measures acceleration and angular velocity giving us position and orientation estimate, albeit maybe noisy or a lot of drift.
- IMU based - at least OSPS, can be conspicuous for everyday use.
- Researchers have taken many approaches in solving this problem. Wearable based - use least amount of sensor possible, hopes of comfort.

{{% /speaker_note %}}

---

## Sparse Wearable Challenge

Goal: Comfortable, Fast, and Accurate Motion Capture System

<div class="multi-column">
	<div class="col1" >
		<img src="figs/concept-osps5.png" alt="Camera based" width="100%" align="center" style="object-fit: contain; object-position: 50% 50%; position: absolute; top:0; left:0;">
		<img src="figs/concept-sparse-bare5.png" class="fragment" data-fragment-index="1" alt="Missing sensor" width="100%" style="object-fit: contain; object-position: 50% 50%; position: absolute; top:0; left:0;">
		<span style="position: absolute; top:46%; left:0;">
			<p>One sensor per segment.</p>
			<p class="fragment" data-fragment-index="1">Less sensor = Missing info</p>
		</span>
	</div>
	<div class="col1">	
		<img src="figs/concept-sparse-imu5.png" class="fragment" data-fragment-index="2" alt="Infer through biomechanical constraints" width="100%" align="center" style="object-fit: contain; object-position: 50% 50%">
		<p class="fragment" data-fragment-index="2">Infer through biomechanical constraints</p>
	</div>
	<div class="col1">	
		<img src="figs/concept-sparse-dist5.png" class="fragment" data-fragment-index="3" alt="Infer through biomechanical constraints" width="100%" align="center" style="object-fit: contain; object-position: 50% 50%">
		<p class="fragment" data-fragment-index="3">Infer from additional measurements</p>
	</div>
</div>

{{% speaker_note %}}
There are challenges associated with using sparse sensor units.
In OSPS, each IMU tracks the pos and ori of each segment.
Lose info of uninstrumented segment.

To cope, two ways.
Infer the state of uninstrumented segments through biomech constraints from state of instrumented segments.
Infer the state of uninstrumented segments through additional measurements.

This paper is of this later type, where we explore the use of additional distance measurements.

{{% /speaker_note %}}

---

## Sparse Constrained KF (CKF)

### Algorithm overview of prior work

<div class="multi-column">
	<div class="col1" >	
		<img src="../../project/sparse-gaitrecon/algo-ckf.png" alt="Sparse CKF" height="400px" style="object-fit: contain; object-position: 50% 50%; position: absolute; top:0; left:0;">
		<img src="figs/algo-ckf.png" class="fragment" alt="Sparse CKF" height="400px" style="object-fit: contain; object-position: 50% 50%; position: absolute; top:0;left:0;">
	</div>
	<div class="col1" >
		<span style="position: absolute; top:0; left:0;">
			<h4>Body Model:</h4>
			<img src="../../project/sparse-gaitrecon/body-5seg.png" align="center" alt="CKF+D Body Model" height="300px" style="vertical-align: 50%">
		</span>
		<table class="fragment" style="position: absolute; top:0; left:0; background: white;">
			<tr>
				<td><SPAN STYLE="writing-mode: vertical-lr; -ms-writing-mode: tb-rl; transform: rotate(180deg);"><p>Pred.</p></SPAN></td>
				<td><img src="../../project/sparse-gaitrecon/samples/ckf-pred-crop.gif" alt="Sparse CKF Prediction" width="100%"></td>
			</tr>
	<!-- cropped original at X 1 Y 98 WIDTH 1646 HEIGHT 489-->
			<tr>
				<td><SPAN STYLE="writing-mode: vertical-lr; -ms-writing-mode: tb-rl; transform: rotate(180deg);"><p>Meas.</p></SPAN></td>
				<td><img src="../../project/sparse-gaitrecon/samples/ckf-predmeas-crop.gif" alt="Sparse CKF Measurement" width="100%"></td>
			</tr>
			<tr>
				<td><SPAN STYLE="writing-mode: vertical-lr; -ms-writing-mode: tb-rl; transform: rotate(180deg);"><p>Cstr.</p></SPAN></td>
				<td><img src="../../project/sparse-gaitrecon/samples/ckf-predmeascstr-crop.gif" alt="Sparse CKF Constraint" width="100%"></td>
			</tr>
		</table>
	</div>
</div>

{{% speaker_note %}}
Before we can proceed with how we incorporated distance measurements,
I will describe our prior work which we was the base of this new approach. 

We tracked lower body segments using 3 imus.
Using a CKF.

CKF takes in input from 3rd party OE and step detection, 
and consists pred, meas, and constraint update.

Animation shows what each part does.
Pred tracks object and by itself suffers from segment drift.
Meas is able to bring the shanks closer to the floor.
Cstr looks like a human walking.

{{% /speaker_note %}}

---

## Sparse CKF - Sample

<img src="gifs/CKF Sample Walk.gif" alt="CKF Sample Walk" height="500px">

{{% speaker_note %}}

Result for free walking was promising.

{{% /speaker_note %}}

---

## Sparse CKF - Weakness

To make it work, we need to make assumptions that may not be practical for certain movements (e.g., Activities of Daily Living or ADLs).

<p>&nbsp;</p>

<img src="gifs/CKF Sample High Knee Jog.gif" alt="CKF Sample High Knee Jog" height="350px" width="450px" style="object-fit: cover; object-position: 50% 50%">

<img src="gifs/CKF Sample Jog.gif" alt="CKF Sample Jog" height="350px" width="500px" style="object-fit: cover;">

{{% speaker_note %}}

However, we needed to make assumptions around pelvis position,
height not stray far from initial height
x y position in between the ankle x y positions.

These assumptions may not be practical for ADLs. 
The idea is, wouldn't it be nice if we can capture not just walking but also other movements.

{{% /speaker_note %}}

---

## Sparse CKF + Distance

### Overview

Distance measurement which can be obtained through ultrasonic or ultra-wide band radio (UWB).

<div class="multi-column">
	<div class="col1">	
		<img src="figs/algo-ckfdist.png" alt="Sparse CKF" height="400px" style="object-fit: contain; object-position: 50% 50%;">
	</div>
	<div class="col1">
		<h4>Body Model:</h4>
		<img src="../../project/sparse-gaitrecon/body-5segdist.png" align="center" alt="CKF+D Body Model" height="300px" style="vertical-align: 50%">
	</div>
</div>

{{% speaker_note %}}

This is where additional distance measurements comes in.
We wanted to see if additional distance measurements can improve sparse MCS.
Using similar setup, but remove pelvis related assumptions, exchanging it with distance measurements.

{{% /speaker_note %}}

---

## Sparse CKF + Distance

Remove pelvis related assumptions. Additional measurement model.

<div class="multi-column">
<div class="col1">
	<img src="figs/body-5segdist-leg.png" alt="Sparse CKF" height="400px" style="object-fit: contain; object-position: 50% 50%;">
</div>
<div class="col1">	

$$ 	\mathbf{H}(\mathbf{x}) = \tau_{k}^{pla} ( \hat{\theta}_{lk} ) \\\\
	\tau_{k}^{pla} ( \theta_{lk} ) = 
		\overbrace{\tfrac{d^{p}}{2} \mathbf{r}^p_y - d^{ls} \mathbf{r}^{ls}_{z}}^{\psi, \text{ hip + shanks}} 
		+ \overbrace{d^{lt} \mathbf{r}_x^{ls} \sin{(\theta_{lk})}
							-d^{lt} \mathbf{r}^{ls}_z \cos{(\theta_{lk})}
							}^{\Lambda, \text{ thigh}} \\\\
	(\hat{d}^{pla})^2 = \tau_{k}^{pla}(\theta_{lk})^2 
		= \psi^2 + 2 \psi \cdot \Lambda + (d^{lt})^2 \\\\
	\alpha \cos{(\theta_{lk})} + \beta \sin{(\theta_{lk})} = \gamma \\\\
		\alpha = - 2 d^{lt} \psi \cdot \mathbf{r}^{ls}_z, \quad
		\beta = 2 d^{lt} \psi \cdot \mathbf{r}^{ls}_x \\\\
		\gamma = (\hat{d}^{pla})^2 - \psi^2 - (d^{lt})^2  \\\\
	\hat{\theta}_{lk} = \cos^{-1}\left( \tfrac{\alpha \gamma \pm \beta \sqrt{\alpha^2+\beta^2-\gamma^2}}{\alpha^2+\beta^2} \right)
	$$
		
</div>
</div>

{{% speaker_note %}}

General idea of meas model is we convert the measured distance along with our knowledge of position and orientation of pelvis and shanks,
to a pelvis to ankle vector (violet line).
Then use that vector as measurement in our CKF.
We refer the audience to the paper for more details of the maths.

Good to note that we did attempt a nonlinear measurement model using the straigth distance between the pelvis and shanks, 
but the experimental results were not promising.

{{% /speaker_note %}}

---

## Sparse CKF+D - Sample

Tested on actual IMU data + simulated distance measurement from Sparse CKF dataset (walking, jumping jacks, speedskater, TUG, jog). 
Most deviation is at the turning motion ($t=3.5 - 5$s).

<p>&nbsp;</p>
<img src="gifs/Sample Walk.gif" alt="Sample Walk" height="350px" width="450px" style="object-fit: cover; object-position: 50% 50%;">
<img src="figs/ckfdist-kneehip-angle-sample.png" alt="Varying sigma" height="350px" style="object-fit: cover; object-position: 50% 50%;">

{{% speaker_note %}}

Good free walking result. Like in CKF, Most deviation is at the turning motion ($t=3.5 - 5$s).

Refer to the paper for more details about the quantitative result. 

{{% /speaker_note %}}

---

## Sparse CKF+D - Sample 

Dramatic increase in performance in dynamic movements. Captures Sagitall knee angles better.

<p>&nbsp;</p>

<img src="gifs/Sample High Knee Jog.gif" alt="Sample High Knee Jog" height="350px" width="450px" style="object-fit: cover; object-position: 50% 50%">

<img src="gifs/Sample Jog.gif" alt="Sample Jog" height="350px" width="500px" style="object-fit: cover; object-position: 30% 50%">

{{% speaker_note %}}

The main benefits can be seem in the dynamic movements.

{{% /speaker_note %}}

---

## Sparse CKF+D - Sample

Is able to locate relative position better. Note: TUG = Timed Up and Go.

<p>&nbsp;</p>

<img src="gifs/Sample SpeedSkater.gif" alt="Sample SpeedSkater" height="300px" width="500px" style="object-fit: cover; object-position: 30% 50%; vertical-align: 50%;">

<img src="gifs/Sample TUG.gif" alt="Sample TUG" height="350px" width="450px" style="object-fit: cover; object-position: 40% 50%">

{{% speaker_note %}}

Is able to locate relative position better.
For example, in TUG trials, the pelvis position was tracked better, in constrast to the plain CKF reconstruction where the pelvis was stuck at chair height

{{% /speaker_note %}}

---

## Sparse CKF+D - Varying $\sigma$

Simulated at different levels of distance measurement noise $\sigma$ (assumed gaussian). Useful from $\sigma \leq 0.1$ m for walking.  Useful from $\sigma \leq 0.2$ m for dynamic movements.

<img src="figs/results-varysigma-bw.png" alt="Varying sigma" height="400px" align="center" style="object-fit: cover; object-position: 50% 50%; vertical-align: 50%;">

{{% speaker_note %}}

Since we evaluated on simulated distance measurements, we also looked at the performance at different level of distance measurement noise, assumed gaussian sigma.

For walking, distance measurement noise sigma leq 0.1 m is enough to improve results. 

For dynamic movements, the distance measurement noise sigma can be even higher. 

There was improvement even at sigma 0.2 m.

It is also good to note however that actual distance measurement noise are not gaussian, so the behavior may change in real life.

{{% /speaker_note %}}

---

## Conclusion & Future Work

* Adding distance measurement is indeed a promising approach
  * Can be implemented using ultrasound or Ultrawideband (UWB) based sensors.
  * Simulated distance measurement needs actual validation.
* Code at [https://git.io/JvLCF](https://git.io/JvLCF)
* Interesting to try with better models and tracking more segments.

<img src="figs/concept-sparse-dist7.png" alt="Infer from distance measurements" height="250px"  width="260px" style="object-fit: contain; object-position: 50% 50%">
<img src="gifs/lgcekf7seg-walk.gif" alt="LG7Seg Sample Walk" height="250px" width="600px" style="object-fit: cover; object-position: 50% 10%">
<p>Infer from distance. &nbsp; Lie Group based 7 segment</p>


{{% speaker_note %}}

This work has shown that adding distance measurement is indeed a promising approach.

Can be implemented using ultrasound or Ultrawideband (UWB) based sensors.

However, validation using actual sensors is still needed.

As part of future work, it will be interesting to use distance measurement with better model representation to track even more body segments.

Preliminary work of tracking 7 body segments using 3 sensor under Lie group representation of the model.

And that concludes my presentation.

{{% /speaker_note %}}

---

## Appendix - CKF+D Quant. Results

Tested on actual IMU data + simulated distance measurement from Sparse CKF dataset (walking, jumping jacks, speedskater, TUG, jog). 

<img src="figs/results-kneehiprmsecc-bw.png" alt="Varying sigma" height="400px" align="center" style="object-fit: cover; object-position: 50% 50%; vertical-align: 50%;">

---

