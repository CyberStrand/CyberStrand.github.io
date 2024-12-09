---
layout: post
title: Oil painting effect based on Blender Geometry Node
description: These are my skills
nav-menu: false
show_tile: false
---
<iframe width="1120" height="620" src="https://www.youtube.com/embed/NjkYFMJRgqE?si=2a5drki66tdyRpEI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<p>This is oil Painting effect build with Blender Geometry Nodes, the materials is collected from famous artist Vincent Willem van Gogh's oil-painting work. This tool can directly apply oil-painting effect to object in Blender with no extra efforts in texturing and shading.</p>

<h2>Here's how it is developed</h2>
<p>I find a artwork of Vincent Willem van Gogh which I like and cut the part that suits for the ocean texture(it is sky actually but work out fine)</P>
<img src="{% link assets/images/oil_painting/source.jpg %}" alt="" data-position="center center" />
<p>Then I get a texture like this</p>
<img width="20%" src="{% link assets/images/oil_painting/tex.jpg %}" alt="" data-position="center center" />
<p>However, when applying a texture to an object the texture is usually tiled to fit for the size of the surface, which leads to a problem of the border line.</p>
<img src="{% link assets/images/oil_painting/tiling.png %}" alt="" data-position="center center" />
<p>We can clearly see the cross lines between the textures when tiled into 2x2 in the picture. To deal with this, I used histogram-preserving blending tool to transform the image to tileable</p>
<img src="{% link assets/images/oil_painting/copy_right.png %}" alt="" data-position="center center" />
<p>And got this:</p>
<img width="20%" src="{% link assets/images/oil_painting/tex_tileable.png %}" alt="" data-position="center center" />
<p>Now the texture is tileable and has smooth transition between different tiles</p>
<img src="{% link assets/images/oil_painting/tileable_tiling.png %}" alt="" data-position="center center" />
<p>Then I use Geometry Node in Blender, which is similar to Shader Graph, to implement the texture to the surface and add more options for customization.</p>
<img src="{% link assets/images/oil_painting/detail.png %}" alt="" data-position="center center" />
<p>Now the ocean is shaded with oil-painting effect</p>
<img src="{% link assets/images/oil_painting/oil_ocean.png %}" alt="" data-position="center center" />