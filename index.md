---
layout: home
title: Home
cv: 'assets/pdf/CV.pdf'
current: '@Dartmouth College'
title: 'Researcher/Technical Artist'
title1: 'Visual Computing Lab -Dartmouth College'
name1: 'Ziqi Tian'
about: 'I''m a graphics researcher focusing on physically based rendering. Currently I''m working at Visual Computing Lab at Dartmouth College advised by <a href="https://cs.dartmouth.edu/~wjarosz/" target="_blank"><b>Wojciech Jarosz</b></a>. <br/><br/> Before coming to Dartmouth, I was a Technical Artist working at Lilith Games and Ubisoft. I''ve participated in the production of <a href="https://www.ubisoft.com/en-us/game/assassins-creed/shadows" target="_blank"><b>Assassin''s Creed: Shadow</b></a> and <a href="https://farlight84.farlightgames.com/" target="_blank"><b>Farlight: 84</b></a>.'
interests: 
  - Physically Based Rendering
  - Geometry Representations
  - Procedural Generation
education:
  - degree: Master student
    school: Dartmouth College
  - degree: B.Sc. Computer Science
    school: Sichuan University
image: assets/images/self/self0.jpg
author: null
show_tile: false
---

<!-- Projects -->
<section id="two" class="spotlights">
	<section>
		<a href="content/darts.html" class="image">
			<img src="assets/images/darts/Finalone.jpg"/>
			<video src="assets/videos/darts_preview.mp4?v=1" muted loop playsinline preload="auto"></video>
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Spectral Rendering Path Tracer</h3>
				</header>
				<p>A physically based path tracer built on Dartmouth's DARTS framework, featuring spectral rendering for dispersion, a custom plastic BSDF, Intel Open Image Denoise integration, multithreaded parallelization, and depth-of-field camera effects.</p>
				<ul class="actions">
					<li><a href="content/darts.html" class="button">Learn more</a></li>
				</ul>
			</div>
		</div>
	</section>
	<section>
		<a href="content/howls-castle.html" class="image">
			<img src="assets/images/3D-modeling/image0.jpeg"/>
			<video src="assets/videos/howls_castle_preview.mp4?v=2" muted loop playsinline preload="auto"></video>
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Howl's Moving Castle: Living Room</h3>
				</header>
				<p>A full recreation of the living room from Studio Ghibli's Howl's Moving Castle, hand-modeled entirely in Maya for a 3D Modeling course — from Calcifer's hearth to the mosaic-tiled walls and candlelit dining table.</p>
				<ul class="actions">
					<li><a href="content/howls-castle.html" class="button">Learn more</a></li>
				</ul>
			</div>
		</div>
	</section>
	<section>
		<a href="content/basement.html" class="image">
			<img src="assets/images/env2.png"/>
			<video src="assets/videos/basement_preview.mp4?v=2" muted loop playsinline preload="auto"></video>
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Environment Art in Unreal Engine 5</h3>
				</header>
				<p>An environment art piece of an abandoned basement, built in Unreal Engine 5 with Quixel Bridge assets, featuring basic keyframe animation for the camera and character.</p>
				<ul class="actions">
					<li><a href="content/basement.html" class="button">Learn more</a></li>
				</ul>
			</div>
		</div>
	</section>
	<section>
		<a href="content/flame.html" class="image">
			<img src="assets/images/VFX.png"/>
			<video src="assets/videos/flame_preview.mp4?v=2" muted loop playsinline preload="auto"></video>
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Stylized Flame Shader in Unity</h3>
				</header>
				<p>A stylized flame effect built with Unity's Shader Graph. Artists can customize the range and color of each flame layer, turning a simple black-and-white texture into a vivid, glowing flame with just a few clicks.</p>
				<ul class="actions">
					<li><a href="content/flame.html" class="button">Learn more</a></li>
				</ul>
			</div>
		</div>
	</section>
	<section>
		<a href="content/oil.html" class="image">
			<img src="assets/images/oil_painting/oil_ocean.png"/>
			<video src="assets/videos/oil_preview.mp4?v=2" muted loop playsinline preload="auto"></video>
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Oil Painting Shader with Blender Geometry Nodes</h3>
				</header>
				<p>An oil-painting shader built with Blender's Geometry Nodes, using textures sourced from Vincent van Gogh's paintings. It applies a convincing oil-painting look to any object in Blender, with no extra texturing or shading work required.</p>
				<ul class="actions">
					<li><a href="content/oil.html" class="button">Learn more</a></li>
				</ul>
			</div>
		</div>
	</section>
</section>

<script>
document.addEventListener('DOMContentLoaded', function () {
	document.querySelectorAll('.spotlights > section > .image').forEach(function (el) {
		var video = el.querySelector('video');
		if (!video) return;
		el.addEventListener('mouseenter', function () {
			video.currentTime = 0;
			video.play();
		});
		el.addEventListener('mouseleave', function () {
			video.pause();
		});
	});
});
</script>
