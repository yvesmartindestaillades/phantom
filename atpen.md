---
layout: inner
title: ATPen
permalink: /atpen/
---
# ATPen, a Mechanical Pen for People with Essential Tremors

*Debiopharm Challenge, Switzerland - May 2021 to Nov. 2021. This project was made in collaboration with Albéric de Lajarte and Dr. André Zacharia, MD, PhD.*

## 1% people can't write due to Essential Tremors

1% of the population suffer from serious essential tremors (ET), a neuro-degenerative disease that causes involuntary shaking movement. ET makes it harder to brush your teeth, drink, write, and so on.

To help people with ET writing, my friend Albéric de Lajarte and I designed an ET-filtering pen. Our idea was selected amongst 80+ projects for the DebioPharm Challenge [1], which financed $5,000 for a 4-months prototype development. We won the technological prize for an additional $5,000.

<img src="/img/posts/atpen/debiopharm_team.jpeg" style="width: 50%; max-width: 600px; margin: 0 auto; display: block;" alt="The 5 teams of challengers. Credit: Debiopharm" caption="The 5 teams of challengers. Credit: Debiopharm">
<div class='caption' style="text-align: center;">
Figure 1: The 5 teams of challengers. Credit: Debiopharm </div>

## Our approach: remove the tremors from writing with a low-pass filter

We filtered out ET from the writing by integrating a low-pass filter to the pen, like a car shock absorber. This is possible because ET typically have a frequency around 8~12Hz, while slow writing is typically below 3Hz [2].


<html>
<link rel="stylesheet" href="/css/images_md.css">
<body>
    <div class="image-container">
        <div class="image">
            <img src="/img/posts/atpen/frequency.jpg" alt="Frequency domain illustration">
            <div class="caption">Figure 2: Green: writing, red: ET, blue: low pass filter. The frequency domains are distinct so we can filter ET out.</div>
        </div>
        <div class="image">
            <img src="/img/posts/atpen/proto1.jpg" alt="Measurement of the writing frequency">
            <div class="caption">Figure 3: Measurement of the writing frequency.</div>
        </div>
    </div>
</body>
</html>

To make the product easy-to-use, inexpensive and robust, we decided to use a mechanical solution. The pen tip is decoupled from the pen body by a spring and damper [3]. The cutoff frequency of the filter was tuned by weighting the tip and tuning the spring stiffness.

## Prototype 1: filtering on X/Y, blocking on Z

At first, we thought that the users would need to have the pen stabilized on the Z axis, and the tremors filtered on the X and Y axis (see prototype 1). We built a large shell, easy to handle, and a spring and damper using TPU 3D printing.

<body>
    <!-- align = "center" -->
    <div class="image-container" style="width: 70%;">
        <div class="image" style="width: 50%;">
            <img src="/img/posts/atpen/proto1_schematics.png" alt="Prototype 1 schematics">
            <div class="caption">Figure 4: Prototype 1, schematics.</div>
        </div>
        <div class="image" style="width: 50%;">
            <img src="/img/posts/atpen/proto1_simulation.png" alt="Prototype 1 FEM simulation">
            <div class="caption">Figure 5: Prototype 1, FEM simulation.</div>
        </div>
    </div>
</body>

User testing revealed that users could keep the pen stable on the Z axis, and that the X/Y filtering was impractical. Also, the range of motion of the pen was too large, and the design wasn't well accepted.

## Prototype 2

We decided to filter along the X axis only, and to reduce the range of motion of the pen. The greatest challenge was to integrate the spring and damper into a smaller pen with the right cutoff frequency. After many iterations, we used a steel blade as a spring along X and a constraint along Y, and magnetic damping based on Eddy's current.


<div class="image" style="width: 80%;">
    <img src="/img/posts/atpen/pen_final_proto.png" alt="The final ATPen prototype">
    <div class="caption">Figure 6: The final ATPen prototype.</div>
</div>

## Our patients liked the prototype 2 better

The final prototype was tested by 3 ET patients, and the results were very positive. The users could write with much better handwriting, and they were very happy with the pen.

To ensure a neutral testing, we had our patients testing the pen every day for a week, at different times. We noticed that the pen was more effective when the patients were tired, which is when the tremors are the worst.

<div class="image" style="width: 50%; align: center;">
    <img src="/img/posts/atpen/test-patient.png" alt="Mrs. Wanner performing standard tests with the prototype 2">
    <div class="caption">Figure 7: Mrs. Wanner performing standard tests (spirals, lines) with the prototype 2.</div>
</div>

## Final results
Writing is easier with our Anti-Tremor Pen (ATPen)
![](/img/posts/atpen/results.png)  
*Figure 8: Writing is easier with our Anti-Tremor Pen (ATPen).* 
