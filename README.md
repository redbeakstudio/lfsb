# LFSB (.lfsb)
File format specification for animated, spatial line-art with shader brushes for 3d and social VR.

# Name
(l) LINE
(f) FILL
(s) SHADER
(b) BRUSH

## Proposal
In recent years, there has been an increase of tools for creating spatialized drawings.
This comes at a time when we would also like to render line art in mobile VR headsets.

After a couple of years of research & discussing with friends who work in the animation and VR industries, it seems that line art is not supported efficently by 3d programs and social VR platforms, but could be. We are proposing to collaboratively work on a specification to provide animated, spatial lines and fills (with shaders) for 3d programs and social VR spaces (metaverses.)

## Working Extension name
LFSB seems to not be already taken by file format names. It would be nice to include 'animated' as a concept, but also would be good to wait a year or so before creating an 'offical' name and extension. For now, we will refer to the file format as `.lfsb`.

## The Dream
Imagine if concept artists working in paint, ink or even 3d painting tools like Tiltbrush, QuillVR, Gravity Sketch, Blender Grease Pencil could easily save and upload their assets, and retain the small file size that comes with recording your movements and lines.

Web developers already know the power of SVG files, Lottie Files (https://lottiefiles.com/) and Base64 png files. Icon-makers, font-creators and others use lines all of the time to build the internet we know. SVG graphics are an xml specification for 2d path data, and Lottie files are a JSON format for describing animated SVG data. These are mobile friendly because the file sizes are small, and additionally, the lines can be optimized to be even smaller. Base64 compression is a way of storing small images encoded for rendering without needing to make a network request.

For the world of non-photorealistic rendering (NPR), this would be awesome to support. It paves the way for sketches to be part of our 3d worlds, and quick sketches too. In the 1940's - 1960's, an opaque painting medium called gouache allowed illustrators to work with the recent developments in color printing. Similarly, early Disney artists used gouache to describe worlds that would become the animated stories we love, with concept art we admire. Check out Mary Blair's work for inspiration.

We could create "spatial gouache" for our social VR experiences, animatics, environment art, architectural drawings, storyboards.

There are incredibly vivacious shader & brush communities for newer illustration & design tools for iPad: Procreate, Affinity Designer, Concepts, Figma. Any Mac based designer is expecting to be able to go back and forth from a tablet to 3d. We would like the workflow for drawing illustrated assets for non-photorealistic rendering in social VR to be easy, seamless, and not block our "flow" states. This will allow for rapid expression of our concepts, and let us "fill in" around the world of mesh objects.

## The Problem
There are many file formats that come close, but the amount of extra work that's necessary to work in a mobile-friendly way, capturing just the data that's needed, and ensuring there are platforms where the work can be seen make it prohibitive, expensive and technically difficult to show this work.

From research, it seems there are a few recommended practices for creating 3d assets, but these recommendations do not support animated lines and fills.

Mesh - A mesh is an assembly of point data stored as triangles.
Line - An assembly of point data.

* GLB - This is the agreed upon interchange format for WebXR. (GLTF 2.0 specification) This supports meshes, but not lines. Supports animation
* OBJ - Supports curves, but no line pressure, colored vertices, shaders, animation. Supports baked materials (.mtl) - Note :Curves do not always render and can be extruded and converted to meshlines. Need to understand why not.

That's it for web-specifications.

Interchange formats attempted by Adobe, Facebook, Microsoft, Apple, Unity, Unreal, animations studios and others (game companies, etc) may have internal efforts for working with spatial line art, but as of the date of writing this, those tools are not available, well-known, or free through basic research (or recommended by any professional 3d artists who already work at Disney or Dreamworks.)

Anything special requires extra rendering & code. If we want to support lines & fills better with ThreeJS, BabylonJS and environments like Mozilla Hubs, AltspaceVR and the proliferation of other social VR environments, it would make sense to build tools, file formats and adapter-libraries so that we have an interchange format that supports this kind of line art & intuitive expression. We clearly love spatial line drawing & want more of it & expect to see it in all social VR worlds, and have it supported as a first-class file format, similar to SVG, PNG, and GLB.

Blender Grease Pencil - Blender has a newer feature called Grease Pencil. Blender supports lines, fills, pressure, color vertices, and applying shaders to the artwork. Originally created for 2d animation & filming to 2d screens. Blender is building native VR support, and working on building and improving lines & fills.

Gravity Sketch - Allows for creating pressure sensitive lines and has basic color support. Exports to .obj files. (Note: the stroke or ink brush can be exported to curves which can be converted to Grease pencil lines & retain pressure, transparency and maybe color data, but not reliably repeatable, due to artist error or other problems.)

"Just convert it to a mesh" - To export outside the Tiltbrush ecosystem, Google has provided an experimental GLB exporter. The process of "meshifying" a line in a 3d program (essentially 'baking' your line) increases the file size at least 10X, and sometimes 80X. This clutters files.

With line-renderer adapters and exporters for ThreeJS, BabylonJS, Unity, Unreal, Maya, Adobe, Mozilla Hubs etc... we could keep the line data intact and allow the artwork to pass through these different systems, similar to how SVG files have allowed easy design communication.

## Extending what already exists

It could be possible to:

* extend SVG to an animated 3d format
* work more with COLLADA files
* extend GLB to support and communicate how lines can be rendered
* extend Lottie files to be spatial.
* render the brush strokes natively in WebGL
* Someday: support natively in Figma, Vectary, Procreate, Affinity Designer, Concepts

We would be content with an adapter system.

Voxel painting - Minecraft has made voxel-painting possible. Voxels seem more like raster points for spatial VR. We hope to learn from innovations in those areas, and also we are really serious about lines.

Performance - It seems like it would be possible to stream point and line data someday.

Anything that makes lines, fills and shader-brushes a possibility for WebXR in social VR.
* If you know of efforts in these areas, please reach out & we can update this document.

## Next steps
We will be continuing to write an adapter for Blender Grease Pencil to ThreeJS.
If you would like to work on that together, please reach out. We also have a platform for publishing the data, which is still very fresh & if you are interested to collaborate with multi-sensory artists, we would love to invite you to play with us while we figure out how to do this (and render quality line art in social VR settings.)

Our experiments are being documented @redbeakstudio on instagram (under highlighted stories: QMN and Storybox.)

## Articles
* https://mattdesl.svbtle.com/drawing-lines-is-hard - Review from 2015. For porting Blender Grease Pencil lines to ThreeJS, we are adapting https://github.com/spite/THREE.MeshLine to support line weight, fills, etc. Blender is still actively developing and improving fills. We seem to be at the beginning of this & we are VERY inspired by @dedouze & have studied his Grease Pencil artwork & have been trying to publish spatial line art out of Blender ever since.

The dream here is really 4d social multisensory "web comics" for VR.

## Work in progress

We will share work in progress & create some git repositories for our adapter libraries.

### Status
Current status of exporting to Mozilla Hubs: Can't do it because Spoke does not support. Need to run own social VR service & set up simple avatar system just to be able to do this & be in a collabortive environment.

Current status exporting to Altspace: Can't do it because MRE doesn't support this file format & need to host own websocket server.

Note: For WebXR work, it should not be necessary to funnel experiences through Unity or Unreal Engine, as is often suggested. We should be able to export from Blender or Gravity Sketch to a format that can be uploaded to Mozilla Hubs, Aframe projects, p5.xr projects, or other mixed-media VR and social VR/AR/MR/XR experiences.

## Animation
Blender Grease Pencil also supports keyframe animation (similar to QuillVR)
Like a GLB file or Lottie file, we should be able to play, pause or stop the animation, and the rest should be able to be modified with client-side scripting for WebXR, and also be triggered in other rendering platforms like Unity or Unreal Enging.

## Environment & Ecosystems
For our purposes, we want the benefits of working with the web: dynamic data, visible source code, social, networked, etc, and we want to be able to be in VR (or not) while making these decisions. This needs to work in a hybrid environment (Mac & PC, Mobile, Tablet & Desktop, Cloud and Local, with and without headsets)

Gravity Sketch (based in UK) is created by designers and they (GS) understand this problem space. Figma also understands that the design process is social and collaborative, and web developer/designers are used to working with a wide variety of platforms, responsive designs, and an array of presentations formats. This seems to be a difference with game developers, who have other requirements (performance, rendering, hardware limits) and animators (who focus on 'whatever gets the shot.')

Designers, writers, storyboard artists, animators, architects, illustrators, set designers, concept artists would benefit from lines and fills being better supported in spatial computing.

We will need to help each other with some new learning curves.
The world is changing, and we have a lot to share & show as we respond to these changes.

## Collaboration, upcoming projects, events
For working on projects in a distributed way, we have a series of projects & events for the rest of 2020.

If you would like to follow along, help or support this project, please do.

This has so far been a labor of love and learning.

This project started from moving to LA and simply wanting to 'mockup' comedy sketches and ideas using new tools such as QuillVR and Tiltbrush. Trying to share work has been incredibly difficult, and as a professional web developer, it seems unnecessarily difficult and inefficient.

Open source projects are all about the community-building, so we hope to make it fun. These projects are part of Quarter Moon Nights, which is a multisensory art club. These line & fill problems for WebXR are our main focus area, as we want to combine line-art with scents and other senses for prototyping multi-sensory experiences.

## Quarter Moon Night Technical Projects, Fall 2020
September: work on lines & fills, research Blender
October: work on ink drawings & methods of outputting static line art to Mozilla Hubs (creating 'letter-writing rooms' for Get Out the Vote efforts) - if outputing line art isn't possible, draft a project proposal for adding this to Hubs.
December: work on 3d-pano sketches (using Draft 360)
January: work on storyboards & animatics with Blender Grease Pencil

If you are a studio, technology company or otherwise and you have an answer to these problems that you are free to share with the world, please reach out. We would love to do a Youtube interview or present any tutorials you might have to anyone interested in spatial line art.

### Test Files
Blender Grease Pencil example file:
Gravity Sketch example file:

## Projects
* Research Tvori's exporters, since Tvori is another strong spatial tool. (Also MasterpieceVR and Dreams from PS4.)
* Create Blender Plugin as open-source repo & develop with examples & community support.
* Create A-frame component for Mozilla Hubs to use experimentally to render Grease Pencil (and support GreasePencil to Mozilla Hubs workflow.)
* Currently: describe a JSON formal for data & deliver data in this format by an API.
* Consider: formats for saving data, shaders, and brushes in a way that can be easiler read and adapted by different programs.
* Build community & outline other requests for this file format.
* Come up with a hashtag for sharing work & projects.
* Connect up more with Grease Pencil.

## Community Participation
Finally, we want artists to be able to speak up and weigh in on how their strokes are rendered in VR.
We are hosting monthly art clubs where we work specifically on this problem for 2020-2021, and will try different methods in collaboration with studios, animators.

Note: we are also working with multi-sensory data, as this is also in an early stage of support in social VR. Part of this need to draw lines came from wanting to mock up synesthetic experiences, and also communicate 'vapor clouds' using Tiltbrush shaders, which meant learning how many problems there can be in this space.

## Table of spatial XR programs and tools & support for lines, fills, shaders & brushes.
Let's make a table surveying the landscape of spatial illustration tools & a more detailed study of existing file formats and changes that could be made.

## Definitions & Scope for first version of file format
It will be helpful to figure out the limit of what we want to support right now vs. not.
Seems like
1. "render lines and fills at all" in WebXR is a good place to start
2. building up to data that's already part of spatial illustration tools
3. add shaders
4. Communicate with social VR programs & existing file format projects for supporting lines & fills better.
5. Share articles and information about what we are learning and any difficulties. 

### Points & Buffers
Point data - a series of x, y, z coordinate data.
  * Can be passed as a buffer object to 3d systems to be rendered
  * Similar to hair & motion line treatments for 3d programs

### Lines
Line art is point data visualized with a line renderer.

We intend to include the following data for each line.

  * Pressure: Weighted & Pressure sensitive. A line can have variable width.
  * UV: Each point has color data. A line can have a rainbow of colors.
  * Alpha: Opacity changes for each vertex color
  * Line width: the width of the line

  For the first version of this specification we are focusing on these items.

## Not a priority right now
There are additional line values that have implications for 3d rendering, but we are not going to worry about these right now, because we are more focused on just supporting lines, fills, strokes.
  * End caps
  * Brush shape
  * Tapering
  * Thickness & thinness algorithms
  * Ray casting - we assume that a point-cloud hull can provide enough boundaries for detecting intersections.

### Fills  
Fills are point data for faces
  * material color
  * made from triangulated faces articulated by line strokes
  * can have texture

### Colors
We might run into some color space issues may need to make recommendations.

### Shaders
Shaders can make lines and fills act like particles and render texture.
Shaders are written in the language of the graphics card and graphics program. (See GLSL, WebGL, OpenGL)

  * Fragment shader - applies texture and coloration
  * Vertex shader - re-orient and re-position point data in response to variables
      * Uniforms - static variables passed to the shader program.
      * Attributes - changing variables for each point

Brushes are assignments of shaders to lines and fills.
Brushes can get complex, and we are here for it!

Brushes are best when shared.

### Animation
  * Lines and fills can be animated in time, through a series of changes in point data & re-rendering.
  * Jump to 'actions' (like GLB files)
  * Frames, layers and groups

Tools like QuillVR are expanding and still exploring the possibilty of defining animations, moments, 'animated gif' like effects using their timeline. Currently, it is possible to export this data as an Alembic file (.abc), with "Curves" exported. We will concentrate on the 'animated spatial line art gifs' version with just a few keyframes, and not elaborate sub-routines. We need more information about these file formats before we can propose animation data and details.

### Scripted animation
There are also times when your animation runs dynamically (generative art), or interactively. For now we will start with just rendering point data with weighted lines, fills and shader brushes. The raw data is all you need to do crazy things with ThreeJS & it's possible to write components that do more effects to the lines. So for now, it seems wise to keep those things separate.

### Performance
For some instances, line art might be all we are sharing in a social VR context, with limited meshes. Because of this, we expect that sharing line art will be performant-enough. The workflow of creating spatial art is still being developed, taught, and explored.

One area that would be helpful will be "Symbol" clones (like in Adobe Illustrator and other programs) for repeating 3d textures. One method for building up spatial lines is to clone your lines, sometimes a lot. This makes the biggest 'mess' of data and most design libraries insist on creating references to our symbols. These are basically 3d stamps.

First drafted by Chach Sikes, 9/1/2020, Los Angeles, CA.
chacha@redbeakstudio.com
