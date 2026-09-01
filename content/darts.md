---
layout: post
title: Spectral Rendering Path Tracer
description: These are my skills
image: assets/images/darts/Finalone.jpg?v=3
nav-menu: false
show_tile: false
---

<link rel="stylesheet" href="{{ "assets/css/twentytwenty.css" | relative_url }}" />
<style>
#one .inner img {
    max-height: 500px;
    width: auto;
    max-width: 100%;
    margin-left: auto;
    margin-right: auto;
}
#one .inner .twentytwenty-container img {
    max-height: none;
    margin: 0;
}
</style>

<h2>Features and Points</h2>

<ul>
  <li>Spectral Rendering (e.g. to render dispersion) — 8 points</li>
  <li>Simple extra BSDF — 2 points</li>
  <li>Intel's Open Image Denoise integration — 2 points</li>
  <li>Parallelization with SmallThreadPool / C++17 Execution Policy / OpenMP — 1 point</li>
  <li>Advanced Camera Effects — 1 point</li>
</ul>

<h2>Motivational Image</h2>

<img src="{% link assets/images/darts/web.jpg %}?v=3" alt="This is a spider web artwork produced by artist Tomás Saraceno" />
<p><em>This is a spider web artwork produced by artist Tomás Saraceno</em></p>

<img src="{% link assets/images/darts/motivation.jpg %}?v=3" alt="Gingko tree in Dartmouth" />
<p><em>Gingko tree in Dartmouth</em></p>

<h2>Spectral Rendering</h2>

<p>Main idea is to convert Albedo to and from Spectrum.</p>

<img src="{% link assets/images/darts/outline.png %}?v=3" alt="self made image" />

<h3>Albedo to Spectrum Recipe</h3>

<p>1. Convert from spectrum to XYZ</p>

<img src="{% link assets/images/darts/equation_spec2xyz.png %}?v=3" alt="Spectral rendering, part 1: Spectra by Christoph Peters" />

<p>2. Convert XYZ to RGB</p>

<img src="{% link assets/images/darts/xyz2rgb.png %}?v=3" alt="Spectral rendering, part 1: Spectra by Christoph Peters" />

<p>By now, given a Spectrum we can calculate a linear-rgb color through integration. We can also convert it to sRGB using Gamma correction. The question is "How to validate?"</p>

<p>Rendered the spectrum in my own path tracer and plot the scatter points in a Jupyter Notebook. By comparing it with the plot in the pbrt book we can see the result is right.</p>

<div style="display:flex; gap:10px; flex-wrap:wrap;">
  <img src="{% link assets/images/darts/rgb2spec_ref.png %}?v=3" alt="spectrum plot in pbrt4.6.1" style="max-width:48%; height:auto;" />
  <img src="{% link assets/images/darts/rgb2spec.png %}?v=3" alt="my plot using integration" style="max-width:48%; height:auto;" />
</div>
<p><em>Left: spectrum plot in pbrt4.6.1. Right: my plot using integration.</em></p>

<h3>Spectrum to Albedo Recipe</h3>

<p>1. Fitting spectrum with a polynomial and calculating the coefficient with an approximation method.</p>

<img src="{% link assets/images/darts/Sigmoid.png %}?v=3" alt="Sigmoid function in pbrt4.6.1" />

<img src="{% link assets/images/darts/polinomial.png %}?v=3" alt="Sigmoid function in pbrt4.6.1" />

<img src="{% link assets/images/darts/rgb2c.png %}?v=3" alt="How to derive coefficient from rgb" />

<p>2. From the equation above, we can see that the coefficient can be directly derived from linear-RGB. Thus, we can just calculate the spectrum by applying those coefficients back to the sigmoid function.</p>

<p>3. But how to validate: RGB → Spectrum → RGB (Convert RGB to Spectrum and back to RGB)</p>

<img src="{% link assets/images/darts/outline.png %}?v=3" alt="self made image" />

<p>By combining the two steps above we can always replace our albedo (RGB) with Spectrum. And now we can reconstruct our code to provide an alternative function for eval(), sample(), texture->color() and so on with Spectrum instead of Color3f as the return value.</p>

<div class="twentytwenty-container">
    <img src="{% link assets/images/darts/jensen_box_mis.jpg %}?v=3" alt="jensen_box_rgb">
    <img src="{% link assets/images/darts/jensen_box_mis_spectral.jpg %}?v=3" alt="jensen_box_spectral">
</div>

<div class="twentytwenty-container">
    <img src="{% link assets/images/darts/web_mis.jpg %}?v=3" alt="web rgb">
    <img src="{% link assets/images/darts/web_spectral.jpg %}?v=3" alt="web Spectral">
</div>

<div class="twentytwenty-container">
    <img src="{% link assets/images/darts/odyssey_rgb.jpg %}?v=3" alt="odyssey mis">
    <img src="{% link assets/images/darts/odyssey_spectral.jpg %}?v=3" alt="spectrum">
</div>

<div class="twentytwenty-container">
    <img src="{% link assets/images/darts/final_2_no_spectral.jpg %}?v=3" alt="Final scene rgb">
    <img src="{% link assets/images/darts/final_256.jpg %}?v=3" alt="Final scene Spectral">
</div>

<h2>Simple Extra BSDF</h2>

<p>I implemented a Plastic BSDF following Mitsuba's documentation in order to render the chess piece material.</p>

<img src="{% link assets/images/darts/bsdf/reference.jpg %}?v=3" alt="Mitsuba 8.2.8. Smooth plastic material (plastic)" />

<div class="twentytwenty-container">
    <img src="{% link assets/images/darts/bsdf/plastic_test_compare.jpg %}?v=3" alt="MIS diffuse">
    <img src="{% link assets/images/darts/bsdf/plastic_test.jpg %}?v=3" alt="MIS plastic">
</div>

<div class="twentytwenty-container">
    <img src="{% link assets/images/darts/bsdf/plastic_test_spectral_compare.jpg %}?v=3" alt="diffuse Spectral">
    <img src="{% link assets/images/darts/bsdf/plastic_test_spectral.jpg %}?v=3" alt="plastic Spectral">
</div>

<div class="twentytwenty-container">
    <img src="{% link assets/images/darts/final_256.jpg %}?v=3" alt="diffuse Spectral">
    <img src="{% link assets/images/darts/Final_Image_512.jpg %}?v=3" alt="plastic Spectral">
</div>

<h2>Intel's Open Image Denoise Integration</h2>

<div class="twentytwenty-container">
    <img src="{% link assets/images/darts/final_2_no_spectral_no_denoise.jpg %}?v=3" alt="diffuse Spectral">
    <img src="{% link assets/images/darts/final_2_no_spectral.jpg %}?v=3" alt="plastic Spectral">
</div>

<h2>Parallelization with SmallThreadPool / C++17 Execution Policy / OpenMP</h2>

<img src="{% link assets/images/darts/paralled.png %}?v=3" alt="Code segment of using SmallThreadPool" />

<h2>Advanced Camera Effects</h2>

<p>Implemented a Depth of Field effect for the camera.</p>

<img src="{% link assets/images/darts/depth_of_field.jpg %}?v=3" alt="Example of depth of field effect" />

<h2>Final Scene</h2>
<img src="{% link assets/images/darts/Finalone.jpg %}?v=3" alt="Final scene" />

<h2>I won the prize!</h2>
<img src="{% link assets/images/darts/winner.jpg %}?v=3" alt="winner prize" />

<script src="{{ "assets/js/twentytwenty/jquery.event.move.js" | relative_url }}" defer></script>
<script src="{{ "assets/js/twentytwenty/jquery.twentytwenty.js" | relative_url }}" defer></script>
<script>
document.addEventListener('DOMContentLoaded', function () {
    jQuery('.twentytwenty-container').twentytwenty({
        default_offset_pct_x: 0.5,
        default_offset_pct_y: 0.5,
        move_slider_on_hover: true
    });
});
</script>
