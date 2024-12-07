---
layout: post
title: Oil painting effect based on Blender Geometry Node
description: These are my skills
image: assets/images/VFX.png
nav-menu: false
show_tile: false
---

<h2>Stylized Flame & Particle VFX</h2>

<iframe width="560" height="315" src="https://www.youtube.com/embed/5FAcLOOJfZY?si=cvZ1jyCtMBnlcXoN" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/a2wkTQfBu7k?si=Q5ZXX9uabGPfYc8r" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<p>This is a stylized flame effect made with Unity shader graph, artists can customize the range and color of different layers of the flame. This shader code can turn a simple black and white 2D texture into a vivid and glooming flame.</p>

<img src="{% link assets/images/shader_flame.png %}" alt="" data-position="center center" />

<p>The shader code is composed of three parts: scrolling effect, masking effect, color rendering.</p>

<p>The scrolling effect creates the illusion of dynamic movement, simulating the way fire flickers and shifts. By manipulating the texture coordinates, the flame appears to 'flow' in various directions, adding realism to the otherwise static texture.</p>

<p>The masking effect is used to refine the edges of the flame, ensuring a smooth transition between the flame itself and the surrounding environment. This technique helps in creating a more natural blend, making the flame feel integrated into the scene rather than just placed over it.</p>

<p>Color rendering is the final key aspect of the shader. By utilizing a combination of gradient maps and dynamic color shifts, the shader can simulate various fire effects—from a fiery orange to a cooler blue flame. Artists can easily adjust the flame's intensity, making it a versatile asset that can suit a wide range of environments, from mystical to apocalyptic settings.</p>

<h3>Key Features:</h3>
<ul>
  <li>Fully customizable flame appearance, including color, intensity, and layer dynamics.</li>
  <li>Optimized for performance while maintaining high-quality visuals, ideal for both 2D and 3D environments.</li>
  <li>Easy-to-use shader graph setup, designed with flexibility for game developers and visual effects artists alike.</li>
  <li>Works seamlessly with Unity's Universal Render Pipeline (URP), ensuring compatibility across various platforms.</li>
</ul>

<p>This stylized flame effect can be used for a wide range of applications, such as environmental lighting, interactive objects, and even character effects like fire trails or burning weapons. The flexibility in customizing the visual appearance allows it to blend seamlessly into different art styles, from realistic to more abstract or stylized settings.</p>

<h3>More VFX Examples:</h3>

<p>In addition to the flame effect, this approach can be extended to create a variety of other particle-based effects, such as smoke, embers, and explosions. By leveraging similar shader techniques, artists can create complex VFX that respond dynamically to environmental conditions and player interactions, all without the need for extensive coding.</p>

<p>Explore the following videos to see these effects in action:</p>


<iframe width="560" height="315" src="https://www.youtube.com/embed/oyBdPF8I8vA?si=dD8nIE5pqHSqrz6i" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/HvN5sMMgu6E?si=TzBUi1DkqHELPYp7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>