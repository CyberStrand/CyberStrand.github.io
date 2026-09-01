---
layout: post
title: Oil Painting Shader with Blender Geometry Nodes
description: These are my skills
nav-menu: false
show_tile: false
---
<iframe width="1120" height="620" src="https://www.youtube.com/embed/NjkYFMJRgqE?si=2a5drki66tdyRpEI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<p>An oil-painting shader built with Blender's Geometry Nodes, using textures sourced from Vincent van Gogh's paintings. The shader applies a convincing oil-painting look to any object in Blender, with no extra texturing or shading work required.</p>

<h2>How It Was Made</h2>
<p>I found a Vincent van Gogh painting I liked and cropped the section that best suited an ocean texture — it's actually a sky in the original, but the brushwork translates surprisingly well to water.</p>
<img src="{% link assets/images/oil_painting/source.jpg %}" alt="" data-position="center center" />
<p>This gave me a texture like the one below.</p>
<img width="20%" src="{% link assets/images/oil_painting/tex.jpg %}" alt="" data-position="center center" />
<p>However, when a texture is applied to an object, it's usually tiled to cover the full surface — and tiling introduces visible seams at the tile borders.</p>
<img src="{% link assets/images/oil_painting/tiling.png %}" alt="" data-position="center center" />
<p>You can clearly see the seams forming a cross pattern where the four tiles meet. To fix this, I used a histogram-preserving blending tool to make the texture tileable.</p>
<img src="{% link assets/images/oil_painting/copy_right.png %}" alt="" data-position="center center" />
<p>The result:</p>
<img width="20%" src="{% link assets/images/oil_painting/tex_tileable.png %}" alt="" data-position="center center" />
<p>Now the texture tiles seamlessly, with a smooth transition between each repeat.</p>
<img src="{% link assets/images/oil_painting/tileable_tiling.png %}" alt="" data-position="center center" />
<p>I then used Blender's Geometry Nodes — a node-based workflow similar to a shader graph — to apply the texture to the surface and expose additional parameters for customization.</p>
<img src="{% link assets/images/oil_painting/detail.png %}" alt="" data-position="center center" />
<p>The final result: an ocean surface shaded with a hand-crafted oil-painting look.</p>
<img src="{% link assets/images/oil_painting/oil_ocean.png %}" alt="" data-position="center center" />