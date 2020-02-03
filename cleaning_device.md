## Testing Cleaning Device Effectiveness

**Goal:** Utilize the phase-contrast imaging technique of Transport of Intensity (TOI) to determine the effectiveness of a student-developed device for automatically cleaning dental retainers.

**Context:** At Northeastern, students engage in a capstone project in their third, fourth, or fifth years, a mechanical engineering capstone group came to the Optical Science Laboratory, asking us to help them measure how effective their device was at automatically cleaning dental retainers. Along with my professor, we decided to use a phase-contrast imaging technique called Transport of Intensity (TOI). Since it is likely that a dirty retainer would reduce the relative intensity of an image, this technique can allow us to compare the relative intensities of an untouched retainer, dirty retainer, and cleaned retainer. The greater the relative intensity, the more 'clean' a retainer is. This allows us to quantify how well the capstone group cleans a retainer.

**Summary:** With help and guidance from my professor, I was able to devise a process that was successfully able to show quantitatively that the student group made a cleaning device that was effective.

### The Technique

Transport of Intensity is a technique that essentially uses images at least three different focuses and determines the amplitude and phase from those images. The image below demontsrates that idea.

<img src = "images/cleaning_toi_idea.jpg?raw=true"/>

Caption: An image demonstrating the technique of transport of intensity <a href = "https://www.osapublishing.org/oe/abstract.cfm?uri=oe-15-12-7165/"> (source) </a>.

To gather the phase from the images, the following equation (the transport of intensity) is used:

<img src = "images/cleaning_toi_eq.png?raw=true"/>

Using open source <a href="http://www.laurawaller.com/opensource/"> (MATLAB code)</a> from the Computational Imaging Lab at UC Berkeley as a basis for unwrapping phase from the above equation, and <a href="https://www.osapublishing.org/oe/fulltext.cfm?uri=oe-18-12-12552&id=199812/"> this research article</a>. From those two sources, I wrote the following MATLAB code:

<img src = "images/cleaning_matlab_code_1.png?raw=true"/>

<img src = "images/cleaning_matlab_code_2.png?raw=true"/>

Caption: The MATLAB code written for unwrapping the phase using transport of intensity.

The MATLAB code can also be found on my <a href = "https://github.com/gajjara/CapstoneGroupCode/" >github</a>.

<img src = "images/cleaning_figure.png?raw=true"/>

Caption: the basic setup of the TOI imaging we did.

For what we needed to do, I setup the following system, where a spherical light source was shined onto the retainer, through a blackout fixture that only allowed retainer light to pass, and a camera behind the retainer holder/blackout fixture. To get the three different focuses, I simply adjusted the camera focus at a length before, at, and behind the retainer.

### The Results

These images show three images of an untouched retainer:

<img src = "images/cleaning_toi_1.jpg?raw=true"/>

Caption: An image focused before the retainer.

<img src = "images/cleaning_toi_2.jpg?raw=true"/>

Caption: A  image focused on the retainer.

<img src = "images/cleaning_toi_3.jpg?raw=true"/>

Caption: An image focused after the retainer.

In order to better view the images, we decided to calculate the phase-amplitude (which is given by Euler's Formula) that we receive from the images. The images show the relative intensity of light received. The following images show the results for the same retainer, with the first image showing the retainer untouched, the retainer dirty, and the retainer cleaned by the group's cleaning device. The greater the intensity in the image the more 'clean' the retainer is.

<img src = "images/cleaning_toi_phaseamplitude.png?raw=true"/>

Caption: The phase-amplitude image of the untouched retainer, represented by __Amplitude*exp(i*phase)__.

The above image is an image for a retainer that is untouched.

The image below is an image of a retainer stained by baby food

<img src = "images/cleaning_toi_dirty.png?raw=true"/>

Caption: A dirty retainer stained by baby food.

The following image shows the retainer cleaned by the cleaning device of the capstone group:

<img src = "images/cleaning_toi_cleanboi.png?raw=true"/>

As seen in the image the group was clearly able to effectively clean the retainer, and in fact made the retainer more clean than when it was untouched.

With the group, we took several images of retainers, and we were able to further prove the effectiveness of the group's cleaning device. Overall, the student group was happy with the results that we gave them.

Credit goes to the mechanical engineering capstone group and my professor Charles A. DiMarzio for their involvement in this project.
