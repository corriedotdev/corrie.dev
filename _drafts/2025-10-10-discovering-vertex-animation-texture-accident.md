---
layout: post
title: 3D Animation - Point-Cloud Playback & Vertex Animation
excerpt: "A 2021 prototype that encoded Kinect point clouds into EXR frames — unknowingly reflecting more data-oriented vertex animation and DOTS pipelines now seen." add in compute shader
categories: [Tech💡]
comments: true
image:
  feature: feature/11.jpg
---

# Coincidence with Point-Cloud Playback and Vertex Animation

In 2021 I was experimenting with rendering a real-time playback from the Azure Kinect lidar feed and built a point cloud player that serialized depth data into EXR bitmaps and allowed for it to be played back.

Each frame stored 3D positions directly in RGBA channels — one pixel per point — and the sequence played back in real time inside Unity (with some bit shifting) At the time, it was a simple way to avoid complex streaming from the containerized `.mkv` format and make point cloud playback easier to handle through a single image. Again to clarify, this was to allow a point cloud captured from a Lidar scanner to position recorded points into a bitmap EXR image. Each row of the bitmap were all the positions and the next row the next for the time buffer. Resulting in interpolation just like a frame animation approach but as its points there are no edges or sides to deform. 

What I didn’t realize then was that this same approach closely mirrors the standard in **Vertex Animation Textures (VAT)** and **data-oriented pipelines** such as **DOTS**. The key component of the research was trying to serialize point cloud recordings in a resource effective way that

1) Could potentially lean into computer vision for AI analysis in the future as more and more areas of the real world become digital twinned, such as object detection from a point cloud scan but use the bitmap vs renderer

2) Lean into optimzation with simple cropping of a bitmap for undistributed point cloud datasets


## Vertex Animation vs Deformed

Instead of a skeleton with deformed skinned mesh data, each vertex in a vertex animation is just point data — streamed and reconstructed at runtime. No caluclations required, unless you are interpolating between frames and this can be done somewhat with Unity through blend shapes and a simple example would be 

{% highlight csharp %}
// Frame 1
skinnedMeshRenderer.SetBlendShapeWeight(0, Mathf.Lerp(0, 100, t));
// Frame 2
skinnedMeshRenderer.SetBlendShapeWeight(1, Mathf.Lerp(100, 0, t));
{% endhighlight %}

That EXR pipeline meant:

- Geometry lived inside a bitmap (EXR = position buffer).  
- Time was represented as rows of pixels or a sequence of textures.  
- Blending between EXRs could create smooth transitions between frames - if normal distributed..  
- Each pixel was effectively a vertex entry in a *structure-of-arrays* layout — the same pattern used in ECS.

What started as a practical workaround for Kinect data ended up being a small-scale prototype of what really happens when you consider VAT or **GPU-driven animation** being a compute shader.

---

## Coincidence

Back in my research I explored how 3D LiDAR and depth data could be stored and replayed using image formats, specifically **EXR**. The idea was simple: treat each pixel as a vector in space.  

3D LiDAR recordings offer a degree of anonymity — the raw points of data themselves don’t reveal a person until processed into world space. By storing these points as **bitmap-based EXR images**, playback could be achieved directly in game engines like Unity or Unreal, rather than relying on proprietary point cloud players.  

Each pixel encoded **XYZ positions** into **RGB channels**, creating a lightweight serialisation format for 3D space. A 16-bit or 32-bit EXR maintained precision while staying lossless. During playback, these images were deserialized and rendered through a custom **particle system** using VFX graph, reconstructing the original point cloud in real time.

This approach also allowed for various optimisations:
- **Pooling points** where can allocate thousands of points at runtime and prevent memory spikes for instantiation 
- **Interpolation** between frames to fill gaps between scan rotations.  

## Point-Cloud LOD System
- **Cropping EXR frames** to dynamically reduce render load while maintaining model structure 
- **2×2 binning**, merging diagonal pixels to reduce resolution while increasing signal-to-noise ratio.

It was an **image-based level-of-detail system**, not far removed from the way **GeoTIFF** or **VAT texture atlases** encode LOD and frame data today.

The same principles  extend beyond static recording — sequencing EXR frames as a real-time animation stream can also work, and reduce the amount of EXR textures needed to be loaded to play a segment of animation. This really leans into the video encode decode processes as well but frames dont have to be for a single appearance on the framebuffer, but instead a frame can contain seconds or a time duration 

For example a 2000x2000 pixel 16bit RGBA EXR will store 2000 x y z positions on each row of pixels. Using a playback standard of NSTC at 24fps this means that this one image can provide 83.3 seconds of point cloud playback.

This is pretty much exactly how a vertex animation works. Adjust vertexes and store into a bitmap image to be played back through a shader.
---

## Mesh Vertices 

The portal in pixel arcade was hastidly done using mesh vertices interpolation using C# on the CPU. Its ok really because its only a few polys. 
{% highlight csharp %}
    t += (forward ? 1 : -1) * Time.deltaTime * speed;
        if (t > 1f) { t = 1f; forward = false; }
        if (t < 0f) { t = 0f; forward = true; }

        // Interpolate vertex positions
        for (int i = 0; i < vertsA.Length; i++)
            vertsCurrent[i] = Vector3.Lerp(vertsA[i], vertsB[i], t);

        meshInstance.vertices = vertsCurrent;
        meshInstance.RecalculateNormals();
        meshInstance.RecalculateBounds();
{% endhighlight %}

## Vertex Shaders

## Computer Shader

---

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Early 2021 prototype of point cloud playback in Unity using EXR frame data — now looking back it feels like a mini data-oriented vertex animation pipeline. <a href="https://twitter.com/hashtag/unity?src=hash&amp;ref_src=twsrc%5Etfw">#unity</a> <a href="https://twitter.com/hashtag/dots?src=hash&amp;ref_src=twsrc%5Etfw">#dots</a> <a href="https://t.co/ZrWXn7PkVx">pic.twitter.com/ZrWXn7PkVx</a></p>&mdash; Corrie (@corriedotdev) <a href="https://twitter.com/corriedotdev/status/1501587367823650816?ref_src=twsrc%5Etfw">March 9, 2022</a></blockquote> 
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

---

