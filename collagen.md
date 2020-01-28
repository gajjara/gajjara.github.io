## Optical Science Laboratory: Collagen Molecule Orientation

<img src = "images/collagen_result_simple_CNN.png?raw-=true"/>

Caption: A collagen monomer that we imaged with its detected orientation.

Note that almost all of the work highlighted here is in a research article in process of publication by Rodrigo P. Alzola, Jose Delpiano, Anuj Gajjar, Rickard Stureborg, Seyed M. Siadat, Jeffrey W. Ruberti, and Charles A. DiMarzio.

Also note that this is not a academic document on this research project here and should not be considered as such. 

**Context, Purpose, and Goal:** 
Collagen is a biomolecule that is present in most tissues of mammals and is important for a wide range of biological functions. Collagen makes up to 25% to 35% of the body's protein content
<a href="https://doi.org/10.1074%2Fjbc.M110709200/"> (Source)</a>. This biomolecule is a triple helical protein that is mostly found as a fibril structure (that forms larger biological structures) <a href="https://jcs.biologists.org/content/joces/120/12/1955.full.pdf/"> (Source)</a>. Collagen can also be found as a set of smaller units, Collagen monomers, these monomers can assemble to form collagen fibrils <a href="https://jcs.biologists.org/content/joces/120/12/1955.full.pdf/"> (Source)</a>. 

<img src = "images/collagen_monomers_img.jpg?raw=true"/>

Caption: An atomic force microscopy (AFM) image of free flowing collagen monomers <a href="https://www.asmicro.com/Applications/Collagen_Monomers.htm"> (Source)</a>.

<img src = "images/collgen_fibril_network.jpg?raw=true"/>

Caption: A transmission electron microscopy micrograph of collagen fibrils <a href = "http://www2.optics.rochester.edu/workgroups/cml/opt307/spr06/xiaoxing/Xiaoxing.html"> (Source) </a>.

In order to image collagen, tranmission electron microscopy is used. The issue with transmission electron microscopy is that it tends to destroy samples after imaging; thus preventing _in vitro_ imaging. Our goal with this research is to prove to the scientific community interested in collagen that fluorescense microscopy is a viable alternative to electron microscopy and can allow _in vitro_ imaging of collagen. This live imaging of collagen can allow the further understanding of the functionality and properties of this biomolecule. This further understanding can unlock further biomedical advances.

Credit goes to Rodrigo Alzola, Professor Jose Delpiano, Professor Juffery W. Ruberti, and Professor Charles A. DiMarzio for leading the project; with credit also going to Rickard Stureborg and Seyed M. Siadat for their involvement in the project.

### The Use of Fluorescense Microscopy

In order to use fluorescense microscopy for collagen, we deciced to attach fluorophores onto collagen monomers, and determine their spatial orientation. This allows us to demonstrate the technique, and the spatial orientation can tell us important information about the monomers. The challenge with imaging the monomers is that since these monomers are at most 300nm long <a href="https://jcs.biologists.org/content/joces/120/12/1955.full.pdf/"> (Source)</a>, and with one of our cameras we can only achieve a resolution of 110nm per pixel; we encounter a sampling problem as we are approaching the diffraction limits of the microscope. If two flurophores can attach to two ends on a monomer, then enough fluorescense can occur that enough pixels with enough intensity can indicate a monomer orientation. A challenge is that two fluorophores may not always attach to a monomer (thus there will be double fluorophore and single fluorophore monomers when we image the monomers). Another is that noise, from the camera sensor, light scattering, and random autofluorescense in the sample can cause certain pixels to cause error in the detection or orientation or single flurophore monomers. Therefore, it is difficult to use iterative techniques  For this reason, a machine learning model is later developed for the orientation detection or single flurophore monomers.

Due to the suscesptibility of noise in the imaging of these monomers, we wanted to simulate the optical system to obtain further understanding of the fluorescense micrsocpy system, and to generate synthetic data consistent with real imaging data. One of my primary roles on this project was to determine this simulation in MATLAB. Along with helping with the development of the orientation detection programs, and the writing of a research article in process of publication on this work.

### Simulating The Optical System

The image below shows a diagram of our optical setup for fluorescense microscopy.

<img src = "images/collagen_optical_sys.png?raw=true"/>

Caption: the optical setup we used for conducting fluorescense microscopy. 

In the optical setup, we use a blue LED light that irradiates onto the collagen sample, and from the fluorophores attached to the collagen monomers, green light is emitted. The emitted light and some blue light from scattering is captured by the camera we use. A set of filters are used for passbands of blue and green light, a passband of blue light is used for the sample illumination, while a passband of green light is used for emitted light. 

To simulate the optics system, I used spectrum on the spectral irradiance from the light source, transmission and reflection in the filterset, the emission and excitation spectrum of the fluorophore that we use, and the quantum efficiency (tells us the probability of photons that turn into electrons). These spectrum were obtained from manufacturers of the equipment we use.

Along with the absorption and scattering coefficents of the fluorophore, a solid angle calculation of the objective lens, the photon energy equation, the fluorophore quantum yield (efficency of photon emission from photon absorption), and the fluorophore lifetime (the time of fluorophore excitation), I was able to conduct a simulation on the amount of photons from emission (green light photons) and photons from scattering (blue light photons) that enter the camera sensor.

Since the green light photons (photons from fluorophore emission) is essentially desired, the photons from emission are considered to be the signal. The blue light photons (photons from scattering) are considered to be part of the total noise in the camera system.
Considering the dark current (the baseline light background noise) noise and the readout noise (sensor noise) in the camera, I was able to get a good estimate of the total noise we recieve in imaging.

The following images shows the results of the optics simulation.

<img src = "images/collagen_opticssim_1.png?raw=true"/>

Caption: The various spectrum used for simulating the optics simulation.

<img src = "images/collagen_opticssim_2.png?raw=true"/>

Caption: The spectrum calculated for the optics simulation.

<img src = "images/collagen_opticssim_3.png?raw=true"/>

### Oriention Detection
Note that I was not primarily involved in this part of the project, credit goes to Rodrigo Alzola and Rickard Stureborg for leading the development of this part of the project. Credit also goes to Seyed M. Siadat for the imaging of the collagen samples.

Using the values of signal and noise I calculated, we were able to generate a set of 20000 synthetic images. This set of images were used to train a convolutional nueral network (CNN) that determined the orientation of monomers within 15 degrees or determined when there was a single fluorophore monomer.

<img src = "images/collagen_synthetic_data.png?raw=true"/>

Caption: A set of synthetic images that we made

Using this CNN, we were able to achieve approximately 70% accuracy with detection.

The following image (also shown above) is an example of a detected monomer (from a real image):

<img src = "images/collagen_result_simple_CNN.png?raw-=true"/>

Caption: a detected monomer from a real image

The following image shows the confusion matrix that we generated of the CNN.

<img src = "images/collagen_confusion.png?raw=true"/>

Caption: The confusion matrix of the CNN that we developed

Despite achieving an accuracy of 70%, the confusion matrix shows that even in an innacurate detection, there is only an error of 15 degrees. Thus we are able to show from the CNN that despite random noise causing error for iterative methods of detection, we are able to detect the orientation of monomers (or single flurophore monomers).

### Fibril Orientation Initial Development
**Back Story**

Outside of this project, but still related to this project, I attempted to detect the orientation of collagen fibrils. There is the potential that  these collagen fibrils can be imaged alongside monomers, further increasing the potential benefits of this research.

Alongside with fluorescense microscopy, we can use differential interference contrast (DIC) imaging, a form of phase-constrast imaging to obtain images of fibrils. A challenge with these images is that it is difficult to seperate signal and noise components in these images. Another challenge is also that when these fibrils are imaged, they tend to be a few pixels wide. A synthetic image below demonstrates these challenges.

<img src = "images/collagen_fibril_syn.png?raw=true"/>

Caption: A synthetic image of a DIC image of collagen fibrils

<img src = "images/collagen_fibril_zoom.png?raw=true"/>

Caption: The red portion of the above image zoomed in

**The Developed Detection Algorithm**

The approach that I developed for this takes the following processes:
- 1) Adaptive histogram normalization to best constrast (This algorithm was developed in the <a href="https://gajjara.github.io/3d_image/"> Rapid 3D Medical Imaging Reconstruction </a> project). This step allows the seperation of noise and signal and components
- 2) 3 x 3 Median filter on the adaptive normalized image. This step allows some noise reduction to occur
- 3) Histogram normalization of filtered image to maximum image intensity (255). From the normalization above and median filter, this allows signal to be in the intensity range of 253-255, and the noise to be in the intensity range of 0-255.
- 4) Thresholding of values past 254 on the twice-normalized image. This reduces most of the noise, while retaining most of the signal. 
- 5) Hough Transform, (transformation to identify lines)
- 6) Overlay of hough transformed image onto original image
- 7) Run through steps 1-6 on the overlayed image, repeat one more time. This allows the identification of the lines in between detected lines from the Hough transform.

The following images visualize the above steps:

<img src = "images/collagen_fibril_step1.png?raw=true"/>

Caption: The adaptive normalization step

<img src = "images/collagen_fibril_step2.png?raw=true"/>

Caption: The median filter step

<img src = "images/collagen_fibril_step3.png?raw=true"/>

Caption: The normalization to maximum intensity step

<img src = "images/collagen_fibril_step4.png?raw=true"/>

Caption: The thresholding step

<img src = "images/collagen_fibril_step5_1.png?raw=true"/>

Caption: The Hough transform

<img src = "images/collagen_fibril_step5_2.png?raw=true"/>

Caption: Detected lines from the hough transform in green overlayed on the inputted image

<img src = "images/collagen_fibril_step6.png?raw=true"/>

Caption: The overlay of the hough transform onto the original image

<img src = "images/collagen_fibril_repeat.png?raw=true"/>

Caption: The repition of steps 1-6 outlined above

As it can be seen that most elements of the fibrils can be detected, but there are still some missing parts of fibrils that are not detected. There is also some false positves present, especially in the image showing the repition of the algorithm. However, this algorithm shows promise and could be used or developed more in the future.

**Positves**

- Repition of steps is promising but needs to be inputted better images
- Iterative steps are also promising but needs to have more noise reduction
- Overall algirthm does not take too long but could use improvement (memory heavy)
- About 80% true positive rate

**Future Scope**

- Create and define homomorphic filter for better filtering of noise
- Explore and add other filters (i.e. n x n median filters)
- Improve combination step
- Run repetition while continually finding ways to improve iterative process
- Create final processing for image returned from repition of algorithm 

### Conclusion and Future Scope

From our work we know that visualizing monomers of collagen with fluorescense microscopy and determing their orientation is not always precise and the process is very delicate and is affected by many factors. Such factors include noise from the scattering of light in a collagen sample, noise in the camera system, potential autofluorescense in a sample, the lack of flurophores attaching to two ends in a monomer, and any mishaps in the making of a collagen sample.

Nontheless, in many cases it is possible to determine the orientation. These approaches are useful for understanding if there is an alignment of monomers in collagen fibril formation. Visualizing collagen monomers in the prescense of a fibril and determining if there is a particular orientation in the attachment process in real time is a potential continuation of our work.

From the conclusion of our paper (in process of publication):

This is one of the first attempts in which single particles of collagen are observed and analyzed with fluorescence microscopy. By being able to observe collagen through this type of microscopy,we can observe collagen in an active
environment. This will allow further understanding of collagen and its behavior and properties,potentially unlocking further biomedical advances.
