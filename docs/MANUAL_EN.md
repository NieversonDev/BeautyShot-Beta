# BeautyShot 82 — User manual

## 1 · Start here

BeautyShot is a Windows application for presenting 3D assets: materials, lighting, cameras, animation and image or video output. This manual describes the Beta 82 interface. Controls depend on the selected object, material family and renderer; a control that is not relevant may be hidden.

### Install and launch
Extract the entire download to a writable folder. Keep the Engine and SculptStudio directories alongside the launcher; copying the executable alone is not an installation. Launch BeautyShot from the extracted folder. Do not run it inside the ZIP. Keep projects and exported images in a separate working folder so that replacing an application version does not replace your work.

The supplied build targets Windows 64-bit and DirectX 12. Progressive and offline path tracing require a supported hardware ray-tracing GPU and driver. DLSS options require compatible NVIDIA hardware. Availability in one renderer does not establish support in another. The reference machine for this release is an RTX 4060 with 8 GB VRAM and 32 GB RAM; this is a tested configuration, not a universal minimum or performance guarantee.

### Your first image
1. Choose File > Import mesh and select a model. Wait for geometry and texture loading to finish.
2. Select a part in Scene, then choose its material slot. Assign the base color, normal and roughness maps in Materials.
3. In Environment, choose an HDRI or a procedural sky. Adjust the lights under Lighting.
4. Navigate to a useful view. Use View > Frame all or frame the selection if the model is outside the view.
5. Create a camera from the current view, set its output size and lock it once the composition is ready.
6. Save the project. In Render choose an image task, camera, output format and destination. Use PNG for a finished display image; choose EXR for linear compositing.

For a texture that already contains painted lighting, use Viewport quality > NPR > Unlit / Hand-painted. Start with white material tint and vertex color disabled. The dedicated workflow is explained in the NPR chapter.

## 2 · Workspace and navigation

The menu bar spans the top. Scene and the contextual Object inspector occupy the left; Materials occupies the right. The viewport is in the center, with its camera selector, transform toolbar and navigation cube. The bottom status bar reports imports, texture loading and triangle counts. Timeline opens below the viewport.

Click an object to select it. Use the Outliner when overlapping surfaces make picking difficult. Frame the selected object before orbiting around a small detail. The transform toolbar switches move, rotate and scale, coordinate space, snapping, and piece selection. Changing the transform space changes the axes used by the gizmo; it does not rotate the model by itself.

Navigation is configurable. Open Preferences > Navigation to choose a profile, orbit center and focus behavior. The footer shows hints for the active profile. Orbit center can use the view pivot, selection or point under the cursor. Focus can frame a selection or keep the camera position. Dolly drag direction and axis are configurable. Copy bindings or start from a preset before making a custom profile.

Shift + right drag rotates the HDRI. Ctrl + Shift + right drag rotates the lighting rig; the first movement locks the rotation axis until release. The navigation cube selects standard views and its Home control returns to the initial view. Hide it from its menu or change its size in Preferences.

Drag panel separators to resize the workspace. Window can detach Scene/properties or Materials into floating windows, move the application to the next monitor and restore the layout. Named panel layouts store useful arrangements. Restoring a layout changes interface placement, not the scene's object transforms.

Number controls accept typed values; Shift gives finer dragging. A modified-value indicator returns a control to its default. Right-click supported control labels to add or remove Favorites. Use the eyedropper in the color picker to sample a visible color; Esc cancels the pick.

## 3 · Menu reference

### File
New starts a project. Open loads a saved project. Import mesh adds geometry to the current scene. Save updates the current project; Save as creates another project file. Package project collects supported external resources for transfer. Recover autosave opens a recovery copy: inspect it and save under a new name before replacing your main project.

### Edit
Undo and Redo traverse edit history. Duplicate creates copies of selected items. Group collects pieces; Ungroup removes the grouping without intentionally deleting its members. Delete removes the selected item; deleting a group also deletes its objects. Isolate and Restore isolate the selection temporarily. Hide, Show all, Lock and Unlock all control visibility and editing. Camera undo/redo is separate from general edit history.

### Add
Primitives include sphere, plane, cube and cylinder. Lights include rectangle, point, spot and sun. Camera creates a camera from the current view; a focus target supplies a movable target for depth of field. Effect submenus are populated from the installed library and include local atmosphere/fog assets, particles, god rays and Draw FX. Global volumetric fog is controlled in Environment. Draw FX starts a drawing mode; Stop drawing or Esc ends it. Fire scatter operates on the selected surface where available.

### Window
History opens camera/history tools. Camera, Timeline, Environment, Render and Preferences open their panels. Move to next monitor changes the application window's display. Scale offers 100%, 125% and 150%. Detach/reattach Scene and properties and Detach/reattach Materials make those panels float or dock. Show/hide Scene and Show/hide Materials control visibility. Panel layouts manages saved arrangements. Restore layout returns the default docking arrangement.

### View
Perspective returns to perspective projection. Orthographic views offers Front, Back, Left, Right, Top and Bottom. Show orthographic grid toggles the grid. Frame all fits the visible scene. Passes opens diagnostic viewport channels. Viewport quality opens renderer and performance controls.

### Viewport camera menu
View through chooses Free view, a named scene camera or New camera from current view. Viewport renderer selects Real-time, Progressive path tracing, Hybrid or NPR. Viewport layout selects Single view, Camera preview, Two views or Four views. View options opens preview size, update frequency and lighting controls. The adjacent small padlock locks or unlocks the active render camera.

### Header buttons
Undo, Redo, Show/hide panels, Preferences and Render provide direct access. Render executes the currently configured output task; it is not necessarily a still image. The timeline icon toggles the timeline. Minimize, maximize and close may be supplied by the Windows title bar, depending on window mode.

## 4 · Projects, imports and portability

Save early, especially before importing a large asset. A scene project stores composition, assignments and settings; it is not a substitute for your source models and textures. Keep those resources in a stable folder. Use Package project when transferring work to another machine, then open the packaged copy to check that resource paths resolve.

Import through File > Import mesh or the supported drop workflow. Use the format filter in the file dialog as the authority for this build. Mesh import and Alembic groom import are different operations; arbitrary animation or grooming data is not interchangeable with a static mesh. Import preferences control splitting by parts/material IDs. A character can therefore appear as a group containing separately editable pieces and slots.

The hologram is a loading preview. Geometry availability does not mean that all textures are ready. Check the bottom progress indicator and wait before evaluating a material or beginning the final render. Very large sources may need substantial RAM, VRAM and loading time even when the final visible asset appears simple.

Reimport selected updates an object from its source while retaining its placement and assigned materials. Reimport only this piece targets a component of a multipart source. The source-part selector and material mapping determine which incoming piece and materials replace the previous ones. Check these mappings before committing a reimport after renaming parts in the authoring application.

For missing files, restore the resource at its saved path or replace the channel/source with the new location. Save a corrected copy and package it again. An autosave is recovery assistance, not a version-control system. Keep dated project backups before destructive changes and before opening older work in a newer beta.

## 5 · Scene, groups and transforms

The Scene Outliner contains environment, lighting, post process, render settings, viewport quality, cameras, groups and model parts. Search narrows the displayed list. Type filters change the list, not scene visibility. Expand groups and objects to reach their pieces and material slots.

Click the eye to show or hide an item. Drag across eyes to change several items in one gesture; one Undo restores that gesture. Lock prevents editing of the relevant item. A camera's small padlock controls its transform. Select a material slot to edit its assignment rather than guessing which overlapping surface received a click.

Group pieces that should move or animate together. Select the group itself for whole-character transform animation. Deleting a group deletes its contained objects; Ungroup is the operation for keeping those objects. Use isolation when a dense scene makes selection difficult, and restore visibility before final output.

The Object inspector exposes position, rotation and scale. Move/rotate/scale gizmos operate in the chosen coordinate space. Snapping helps repeat regular offsets. Negative or strongly nonuniform scale can affect normals, thickness and procedural patterns; verify those materials after scaling. Explode view separates pieces for presentation without requiring you to manually arrange every part.

Pivot editing changes the center used for transformations. Choose among the 27 bounding-box positions, enter coordinates, copy a pivot, find the nearest vertex or pick a vertex in the viewport. Exit pivot editing before moving the object itself. Bake pivot / set object origin applies the pivot as the object's origin while keeping the mesh in place. Check the pivot before a turntable: an off-center pivot causes an orbit rather than an in-place rotation.

Mesh / Subdivision contains the available geometry refinement controls. More geometry is not automatically more useful: inspect the silhouette and shading, and retain the original source for reimport. Render visibility and editor selection are different concerns; confirm which objects remain visible in the output.

## 6 · Material library and presets

The library lists scene materials and available preset categories. Search, categories and Favorites help find a preset. Change thumbnail size for browsing. A thumbnail is an illustration of a preset under its preview conditions, not a guarantee of its appearance on a different model, light rig or renderer.

Drag a preset onto a surface or Outliner material slot to assign it. Alt-drag opens scope choices. Double-click adds an editable material to the scene library. Confirm the intended slot before editing: several objects may share the same scene material, so changing it can affect all of them. Duplicate a material when one object needs independent settings.

Use material categories and Move to to organize selected entries. Favorite marks frequently used materials. Save/export a preset to reuse a look, and import a compatible preset to add it to the local library. Keep its dependent textures together when sharing it. A material preset does not contain the entire lighting and camera composition.

Open Material Graph or Open construction inspects a material's editable graph. Basic artist controls expose common adjustments; Advanced lists actual parameters of the prepared parent. These views edit related material data, not separate copies. Some presets contain specialized texture types or compiled switches that require a prepared variant rather than a file replacement.

Prismatic Crystal is a material look for assigning to chosen surfaces. It is not a global NPR style. Apply it only where a crystal appearance is wanted; use the NPR selector for a viewport-wide artistic mode.

## 7 · Texture channels and color interpretation

Choose the material, then assign maps to their matching channels. Base color describes surface color; normal describes direction detail; roughness controls highlight spread; metallic identifies metal; AO controls ambient occlusion; emissive adds emitted color. A packed map needs the correct source channel for each destination. Do not treat every grayscale texture as opacity.

Each map can be enabled or disabled without discarding its source, tiles or adjustments. Open source folder locates the original file. Reset map restores inherited/default settings where available. A preset texture may be inherited until replaced. Source channels choose R, G, B or A. Color-space overrides create a compatible converted texture rather than changing an incompatible shader sampler in place.

Base color usually represents color data; roughness, metalness, AO and normal maps represent linear data. Follow the exporting application's convention instead of changing exposure to compensate for an incorrectly interpreted map. Normal convention can be DirectX or OpenGL; use the normal interpretation control when bumps appear inverted. Strength changes the detail intensity.

Roughness or Glossiness selects the intended map interpretation. Glossiness is inverted into roughness as linear data. Levels/gamma and inversion are channel adjustments, independent of scene exposure. Metalness threshold can turn a mask into binary metal/dielectric regions; leave it disabled for intended continuous values. AO has its own levels. Channel preview isolates data for diagnosis.

UV scale, detail tiling, detail normal, height/parallax and texture sharpening affect sampling or apparent relief. Native UV/UDIM color sampling must remain consistent with the source. Before blaming a seam on the shader, inspect UV padding, normal convention, map channel and the source texture. Surface paint and vertex color can multiply the base color; disable Use vertex color when comparing the texture alone. Loading a base map uses the texture-oriented workflow, but existing project/preset settings should still be checked.

Map tint and base-color levels are deliberate artistic adjustments. For a faithful source comparison start with white tint, neutral levels, correct color space and no vertex modulation. Display transforms and post processing can still change the image shown on screen.

## 8 · Opacity, black pixels and glass

Black color and transparency are independent. An opaque black pixel should remain a visible black surface. A coverage mask controls whether that surface exists. Base-color alpha may supply coverage when the material is configured to use it; the RGB brightness is not a substitute for that alpha.

### Choose a coverage mode
Opaque keeps the surface solid. A retained opacity map is ignored by an opaque material, including in NPR. Cutout / Masked removes pixels according to coverage and suits leaves, lace or hair-card cutouts. Translucent allows partial coverage but has different sorting and rendering behavior. Choose Glass for see-through glass or clear plastic rather than trying to imitate it only by lowering the opacity of a scattering surface.

### Diagnose black regions disappearing
1. Select the affected material slot and inspect Opacity mode.
2. For a solid object choose Opaque. Inspect the Opacity channel and the Base color alpha source indicator.
3. View the original texture's alpha separately from RGB. A PNG may contain unintended zero alpha even when its RGB image looks correct.
4. If cutouts are intended, keep Masked and supply the authored coverage map. Do not remove genuine alpha to hide a problem elsewhere.
5. Export a small RGBA PNG and inspect it over a checkerboard. A black background in an image viewer can conceal the difference between black pixels and transparent pixels.

Subsurface and thickness are not coverage. A white SSS mask enables scattering; black suppresses it. Thickness changes the distance light travels through material. For a bottle start with coverage 1 and adjust absorption distance, transmission tint, IOR and roughness. Glass needs suitable geometry, thickness and a useful environment to reflect. Raster and path-traced glass may differ; a thin plane is not a physically closed volume.

For transparent output select an alpha-capable format and enable the output's alpha option. JPEG and ordinary MP4 do not preserve transparent backgrounds. The material's coverage and the image's background alpha are separate settings.

## 9 · Material families and advanced controls

Choose a family suited to the surface: general PBR, skin/subsurface, metal, clear coat, cloth/fuzz, glass, hair cards or eyes. Parameters are family-dependent. Start with the basic controls, then use Artist and Advanced to expose the prepared parent's additional capabilities. Search parameters and read the parameter's type before changing it.

Skin scattering profiles, transmission strength, thickness and scattering tint control subsurface response. Clear coat adds another reflective layer with its own roughness. Cloth/fuzz controls soft fiber response. Hair-card opacity cuts out the card; it does not create individual groom strands. Eye controls include iris mask and depth. Glass recipes provide starting points, not a replacement for correct geometry.

Lighting groups separate direct illumination and specular response. One-sided/two-sided surface settings change back-face behavior. Emission color, map and strength control self-lit content. To glow only selected materials, mark Selective bloom on those materials and set its radius/strength in Post Process. Scene bloom can be combined with it; a bright emissive material is not automatically a useful area light in every rendering mode.

Procedural/clay materials may expose automatic scale, tiling and relief. Automatic scale fits detail to the model; adjust it if the source units produce inappropriate detail size. Advanced scalar, vector, color and texture entries edit actual prepared material parameters. Static switches marked compiled cannot be toggled into a shader permutation that was not shipped. Cube, volume and virtual textures may require a prepared variant.

The capability inspector describes the real prepared rendering family. It should not be interpreted as a promise that arbitrary Unreal material graphs can be compiled in the packaged application. Keep a duplicate material before changing family, and compare its channels after the switch.

## 10 · Material graph and surface painting

Open Material Graph from the material library to inspect construction. Select nodes to edit their inputs and connect compatible outputs to inputs. Keep the final output connected. Published artist controls refer to the same node values shown in the graph and, when animatable, the timeline.

Use Group selection (Ctrl+G) to organize nodes and Ungroup (Ctrl+Shift+G) to expand them again. Save selection as preset stores a reusable construction. Insert Blend material provides the supported layered blend workflow. A graph built on a prepared family must stay within that family's runtime capabilities; it is not a general Unreal shader compiler.

To animate a material value, add or use an animatable Float node, expose the intended scalar/color control and create its material track. Invalid native parameter names are rejected. Scrub the timeline to inspect the same published value, and save the project to preserve both construction and animation. A static switch cannot be animated as though it were a scalar.

Surface painting offers a brush and face selection. Configure radius, strength, falloff, color, operation and channel. In Brush mode the left button paints; in Faces mode click or box-select, Ctrl adds and Shift removes. Navigation keeps its configured shortcuts. Fill object / selected faces applies the current operation to the selected scope. Slot-only limits work to the selected material slot where enabled.

Choose a paint material or add a painted material layer for a blend workflow. Preview helps inspect the painted channel. Vertex painting requires enough vertices to represent detail; it is not a new UV texture baked at an arbitrary resolution. Restore normal display after inspecting paint masks and keep the source model for reimport decisions.

## 11 · Groom and curve imports

Alembic groom import creates strand geometry from compatible curves. Set units and the up axis in Preferences before import if the source convention is known. Auto units is a starting point; inspect scale against the character. Z-up and Y-up describe different source coordinate systems.

Select the groom and open Groom geometry. Density interpolates additional strands between compatible nearby source curves. It does not recover a hairstyle that was not present in the source. Adaptive curve sampling uses more points where curvature requires them; a lower angle retains more curl detail while straight segments need fewer points.

Width multiplier scales original vertex widths, preserving taper from compatible sources such as XGen. Inspect roots and tips as well as the overall silhouette. Large widths and excessive density can make a groom appear solid and increase memory cost.

Rebuild rereads the source file with the current geometry settings. Restore original rereads it at 1× density and original curve sampling. Keep the Alembic file accessible; changing controls that rebuild geometry requires the source. Test a small crop before raising density across a full groom.

## 12 · Lights and lighting rigs

Add rectangle, point, spot or sun lights from Add or the Outliner light control. Rectangle lights provide area-shaped highlights, point lights radiate from a position, spots have a cone and sun lights supply a directional source. Select each light to edit its transform, power and color. Temperature presets provide common color starting points; tint remains an artistic choice.

Use source size and softness controls to shape highlights and shadows where supported. IES profiles shape photometric distribution; Gel/Gobo textures shape or color projected light. Load compatible resources and keep them with the project package. A gobo is not the same as changing the environment background.

Light Controller and rig controls move a group of lights coherently. Rig rotation can be reset and the rig framed. Rig Power (EV) changes the group's exposure-like intensity. Follow object keeps the configured light relationship to a target. Inspect the target and center before rotating a rig around a large or off-center scene.

Specular controls can hide a light's direct highlight while keeping its illumination. For point, spot and rectangle lights, floor-only specular controls reduce unwanted floor reflections without removing object highlights. Lighting groups on materials can further separate direct light and specular response.

Volumetric scattering and volumetric shadows affect participation in fog. They are useful only when an appropriate volumetric medium is present. Shadow maps, virtual shadow maps and ray-traced shadows are quality choices in Viewport quality, not interchangeable artistic light types. Use a small render to compare the chosen final backend after changing light or shadow settings.

## 13 · Environment, floor and effects

Environment controls the HDRI, sky, ground and background. HDRI rotation changes the direction of environmental lighting. Intensity changes illumination; background visibility controls whether the environment appears behind the model. A hidden background does not necessarily disable its lighting. Sky Light enables the ambient contribution from the chosen environment.

Procedural sky provides an alternative sky source. Ground controls the floor's visibility and appearance. Adjust floor material/reflection rather than darkening the entire image to suppress a bright floor. Scene ambient occlusion adds indirect contact shading and is independent of material AO maps.

Camera backdrop can use a solid color or image. Cover fills the crop and may trim edges; Contain fits the whole image and may leave margins; Stretch fills by changing aspect. Match camera crop to image changes the output composition to the image ratio. Flat background and Backdrop at depth behave differently with camera movement and scene placement.

Volumetric fog is enabled in Environment. Local atmosphere effects are separate scene objects with their own artist controls. Use uniform object scale where requested by the effect. Radius controls a spherical volume; zero densities remove the fog contribution. Advanced controls expose the prepared effect parameters, which vary by asset.

Draw FX creates a stroke-based effect that can then be moved, rotated and scaled. Select a new stroke from Add > Particle Effects > Draw FX; Esc ends drawing. Natural/stylized flame options, color, direction, speed, gravity, linked light, custom mesh and material override appear only on compatible effects. Restore Default material to remove a custom override. Animated particles and effects need warmup when rendering a settled state.

## 14 · Cameras, lenses and multiple views

Free view is the navigation view and is not a saved render camera. Create a camera from the current view to preserve a composition. Look through camera activates it. A camera frame identifies the render crop; a locked camera uses the locked-frame indication. Unlock before editing its transform, then lock again to avoid accidental changes.

Camera controls include orbit/yaw, tilt, distance, precise transform and aim at scene center. Perspective uses a lens/FOV; orthographic projection removes perspective size change with depth. Choose a standard orthographic direction from View or the cube. Orthographic width controls framing; it is not a focal length.

Output / crop sets width, height and presets. Preview camera crop shows the intended image boundaries. Frame margin, guide color, opacity and outside shading help compose without changing final pixels. Duplicating a camera can also duplicate its keyframes; deleting the camera removes that viewpoint. Camera history provides a separate way to recover navigation/composition changes.

Depth of field depends on focus distance, aperture and the selected lens/projection. Use autofocus or a focus target when the subject moves. Bokeh/lens shape controls the appearance of out-of-focus highlights. Confirm focus at the final output resolution: a small preview can hide a missed focus plane. A focus target must remain correctly assigned and animated if the subject moves away.

Single view, picture-in-picture camera preview, two views and four views are workspace layouts. Preview size and updates per second trade fidelity for responsiveness; full lighting can increase preview cost. Each view has its own interaction context. Select the intended view before manipulating an object or light. A workspace with several previews does not itself create a multi-camera render queue.

Camera look / local override gives the camera its own post-process settings. Enter that camera before editing its local look. Scene post process remains the fallback for cameras without an override. The active camera selection in the Render panel determines which composition is exported.

## 15 · Post processing and color management

Choose Scene post process for a common look or Camera look / local override for a particular camera. Check the target before changing exposure or color. Reset all post-process effects resets the selected scope; save a look preset first if you want to reuse it.

Exposure/EV sets image brightness. White balance temperature and tint correct or stylize color. Saturation, contrast, gamma, gain and offset change tonal response. Image curves provide channel/tonal shaping; neutral curves are a useful comparison point. Color grading can be disabled to diagnose whether a color shift comes from grading or the material.

Bloom creates glow around bright values. Selective bloom restricts an additional glow to marked emissive materials; choose whether to combine it with scene bloom. Vignette darkens the image perimeter. Sharpen, clarity and clarity radius affect detail contrast. Chromatic aberration/scene fringe separates color at edges. Grain size and amount control film-like texture.

Film texture effects include additional grain, chroma and animated grain where exposed. Zero intensity disables an effect. Animated grain is stable per output frame; it is different from path-tracing sampling noise. Clear legacy extra effects removes old effects retained by older scenes so the visible controls account for the look.

Color lookup loads a .cube LUT and offers an intensity blend. The display transform, including the available OCIO/tone-mapping choices, affects viewport and display image output. Linear EXR beauty and data passes have a different purpose: they are intended for a color-managed compositor, not direct comparison in an unmanaged image viewer. Apply the intended display transform when viewing them.

CMAA2 spatial antialiasing can run alone or after the selected GPU AA; combined mode retains that AA. It treats spatial edges, not illumination noise. Calibration and ROI tools help compare light/texture response. NPR's internal effect processing is separate from scene/camera post; changing a style should not require overwriting the scene's grading setup.

## 16 · Viewport renderers and performance

Real-time uses the interactive lighting path and is useful for scene assembly. Progressive path tracing keeps ray-traced preview active while navigating and refines after the view stops. Hybrid navigates in real time and blends in the completed path-traced result after a pause. NPR applies the selected stylized surface and/or internal post effect. Choose a renderer in Viewport quality or the viewport camera menu.

Progressive and Hybrid depend on hardware ray tracing and the shipped shaders. If unavailable, check the device/driver and a small scene first. A scene that renders offline can still exceed interactive memory or initialization constraints. Dense meshes, large textures and multiple previews all contribute to resource usage.

Progressive reconstruction offers Auto/neural preview or Native resolution/neural preview. The Auto label can mention DLSS on supported hardware. This is not a claim that NVIDIA Ray Reconstruction is implemented. During interaction the preview favors responsiveness; stationary refinement restores detail. Material edits invalidate affected accumulation, so allow the image to settle before evaluating fine differences.

Viewport quality presets include Reference, Presentation, Studio and Edit. Lighting/reflection quality, shadow method, geometry and depth of field are separate controls. Performance/idle power controls regulate background or idle work. Lower preview size or update frequency for additional camera views if they are consuming resources.

Viewport quality and offline render quality are separate. Increasing offline samples does not make navigation slower until rendering starts, and a fast viewport capture is not a substitute for offline sampling. Choose the final output backend deliberately. For an NPR-style final image use the NPR-compatible deferred output path; path tracing is a different renderer and should not be assumed to reproduce screen-space NPR effects.

## 17 · NPR styles and hand-painted textures

Select Viewport quality > NPR, then a style. Preset names describe looks rather than artists. Existing projects keep their internal style identity when names change. Effect enabled toggles surface styles; NPR amount controls compatible post effects. Controls vary by style: do not expect a lighting slider to affect an unlit texture.

### Traditional Unlit / Hand-painted
Assign the painted texture to Base color, use white tint and disable vertex color unless the source deliberately uses it. Choose Unlit / Hand-painted. This displays painted base color without scene-light shading, outline, brush overlay or specular highlights. Preserve intentional alpha with Masked; choose Opaque for a solid model. It is suitable for textures whose highlights and shadows were already painted in an application such as 3DCoat. Display transform, tint and scene/camera post can still alter the final displayed color.

### Style catalogue
- Velvet Cel: stepped character shading and controlled shadow boundaries.
- Flat Cel: simplified flat character shading.
- Layered Gouache: layered painted response with brush detail and parallax controls.
- Bristle Paint: brush/height detail and painted reflections.
- Four-Tone Canvas: a compact painted tonal palette with its material inputs.
- Painted Light: painterly lighting response.
- Living Canvas: world/character brush patterns and paint color blending.
- Illustrated Character: illustrative character shading.
- Hero Brush: graphic character shading with brush control.
- Noir Ink: dark ink treatment with light/dark separation.
- Manga Dots: monochrome tone-dot treatment.
- Pop Halftone: lit, midtone and shadow palettes/maps with halftone patterns.
- Etched Comic: print/hatch treatment with exposure, saturation, contrast and brightness controls.
- Chromatic Print: graphic print effect, with optional background/floor inclusion.
- Graphite Study: pencil-like graphic treatment.
- Crosshatch Shadows: hatching controlled by shadow threshold.
- Retro Palette: grid division and color-level reduction.
- Pixel Mosaic: square pixel size and luminance levels.
- Astral Shimmer: animated edge emission/shimmer over character color.

### Calibrate for the subject
Start at the final output size. Outline width is measured in pixels; print dot size and tiling need to suit the framing. Large dots on a small character can hide its face. Compare subject and background separately, and use Include background and floor only where the style offers it. Preserve model colors when desired instead of using a replacement palette.

Surface styles may use an NPR key-light direction that follows a scene sun. Azimuth/elevation and style-specific shadow threshold/sharpness control the look. Post styles respond to the scene's rendered image. Brush density, strength, parallax and painted reflection are artistic controls, not extra geometry quality settings.

Material-specific NPR inputs include lit/midtone/shadow colors or maps, a packed brush atlas, character face masks and a shimmer mask. Packed brush channels are RG stroke normals, B pigment/height and A bristle detail. Character face masks use R front-right, G front-left, B back-right and A back-left; AO contributes to the boundary. A generic model without these authored inputs cannot reproduce every feature of a specially authored character shader.

To render, keep NPR active, select a deferred final render or direct viewport capture, and export a small comparison first. PNG is the straightforward display-image comparison. Linear EXR bypasses some display processing by design; do not judge it in an unmanaged viewer. Specialized graph materials may retain their own prepared behavior rather than accepting every global surface override.

## 18 · Timeline and animation

Open Timeline from Window or the header icon. Set the frame range and FPS before authoring a timed shot. FPS defines how frames map to time. Scrub the playhead to inspect a frame; playback previews the animation but is not the same as exporting every frame offline.

Select the object, group, camera or animatable material control whose track you want to edit. Add keys for the intended values at the current frame. Move the playhead, change the value and add the next key. Use a group track to animate a multipart character as one unit instead of selecting every material-ID piece separately.

Interpolation determines the transition between keys. Whole track applies the interpolation choice across that track. Use held/step-like changes for abrupt switches and smooth interpolation for continuous movement where offered. Inspect intermediate frames: correct endpoints alone do not prove a good trajectory. Motion-path display helps inspect animated object movement.

Camera tracks can animate composition and supported lens/focus controls. A camera's local post-process override is edited while viewing that camera. Material tracks use published animatable values or compatible Float nodes. Arbitrary native static switches and unsupported graph operations are not timeline channels.

Imported animation depends on the supported importer and source data. A grouped static character does not become a skeletal rig merely because its group can be transformed. Use the source application's animation workflow for unsupported deformations, then import a supported representation.

For final output choose Timeline in the relevant render workflow. Direct capture records the timeline range at the chosen output rate while preserving duration. Offline rendering samples frames through the render pipeline. Turntable is a separate task using a selected object/group and pivot; it does not require manually adding a rotation key to every piece.

## 19 · Render workflow and file formats

Open Render and choose the workflow before pressing the header Render button. Direct viewport output uses the active view's current pixel size and quality. Offline / Movie Render Queue uses the configured output resolution, camera and sampling. The camera selector, task and backend are separate decisions.

### Direct viewport
Choose an image or recording task. Live recording captures navigation with the active camera's normal controls; Stop and save finishes it. Discard deletes that capture's temporary output, not existing files. Turntable records one complete rotation of the chosen objects/group around its pivot. Timeline records the current range. Selection outlines and gizmos are hidden from the capture.

### Offline output
Choose a camera, output width/height or resolution preset, format and destination. A still writes one image. Timeline writes the animated range. Turntable writes the orbit task. Choose Deferred/Lumen for compatible real-time/NPR presentation or Path Tracing for the physically traced beauty. Check warmup for temporal effects before increasing samples.

PNG is a lossless display image and can carry alpha when enabled. JPEG is compact but lossy and has no alpha. EXR stores linear HDR/compositing data; it requires appropriate viewing transforms. MP4 is practical for ordinary playback and does not provide transparent output. GIF is lightweight but palette-limited and can band or dither. The alpha-capable MOV option is intended for compatible compositing software; confirm the target application's codec support.

Use image sequences when you need individual frames or robust compositing. Do not rename an extension to convert a format. Large output resolution, multiple passes and long sequences increase disk requirements. Choose an empty named output folder for each version so that frames from separate renders are not confused.

After rendering, verify the actual files: size, dimensions, frame count, first/last frame, alpha and the chosen camera. View a transparent output over a checkerboard. A successful progress indicator does not tell you whether the selected task or framing was the one you intended.

## 20 · Offline quality, passes and camera queue

Render quality presets provide starting points for Studio, Final, Reference and Path Tracing. Spatial samples improve sampling of the output; warmup allows temporal history and effects to settle before writing frames. Increasing either costs time and can increase memory pressure. Do not increase both blindly to correct an incorrectly assigned texture or opacity mode.

Path tracing samples per pixel govern convergence; light bounces govern how many interactions paths can make. Too few bounces can change glass and indirect light. Firefly maximum intensity clamps bright outliers, but an aggressive value can remove legitimate highlights. The path tracer denoiser reduces noise and may soften details. Compare a small crop with sufficient samples before committing a long sequence.

EXR beauty is linear. Deferred data passes include BaseColor/DiffuseAlbedo, WorldNormal, Roughness, Metallic, Specular and Depth, with additional channels shown when supported. These are not all beauty images: normals are directions, depth is distance and roughness is scalar data. Avoid applying a beauty display transform to a data pass used for computation.

Lighting-component AOVs are additional renders of the same frame, while data passes come from the G-buffer. They can add substantial render cost. Multilayer EXR stores multiple channels in one compatible container; separate outputs are useful when the compositor does not support that layout. Beauty only / preserve DOF avoids unnecessary diagnostic passes. Path tracing exports its linear beauty and hides deferred-only data passes.

Camera queue renders named scene cameras one at a time to PNG, EXR or JPEG. Use the queue command instead of assuming multi-view previews will be exported. Cancel queue ends the queue and restores the prior composition. Inspect the output names and camera count before sharing. Orthographic view export provides the selected standard views; check framing and scale for the intended presentation.

For NPR, compare a representative still and a short sequence at the intended dimensions. Screen-space dot/outline size can change its perceived scale with resolution. For hand-painted work, keep the Unlit style active and avoid adding lighting-based shading through an unrelated renderer.

## 21 · Preferences, shortcuts and customization

Preferences is available from Window and the settings icon. Language selects English, Português (Brasil) or Español. Some specialized asset/control labels may remain in their original language. Interface scale, opacity, interface color, outline, slider and text colors customize readability. Restore appearance returns the appearance defaults.

Import preferences include splitting behavior and hologram base color. Alembic preferences include units and up axis. View cube size and gizmo size change interaction aids; + / − can adjust the gizmo where assigned. New-light settings define starting behavior for subsequently created lights. Existing lights should be checked independently.

Keyboard shortcuts can be edited, cleared and restored through the shortcut editor. Navigation profiles have their own bindings and focus/orbit behavior. If a shortcut does not work, check input focus and the assigned binding before assuming the action is unavailable. Typing inside a number field should not be confused with a viewport command.

Common defaults: Ctrl+N New; Ctrl+O Open; Ctrl+I Import mesh; Ctrl+S Save; Ctrl+Shift+S Save as; Ctrl+Z Undo; Ctrl+Shift+Z Redo; Ctrl+R Render current task. In the graph Ctrl+G groups and Ctrl+Shift+G ungroups. P selects perspective through the View command. Esc cancels active pick/draw operations. User bindings can override defaults; the shortcut editor is authoritative for your installation.

Favorites collect supported controls via right-click on their labels. Named panel layouts are useful for material editing, animation and multi-monitor work. Keep interface customization separate from scene presets: a lighting/material preset does not necessarily restore panel placement.

## 22 · Troubleshooting and reporting a problem

### The texture is darker or tinted
Check Base color versus another channel, source color space, white material tint, vertex color, exposure, camera-local grading and LUT. Use Unlit / Hand-painted to remove scene-light shading for a painted-texture comparison. Reset one category at a time so the cause remains identifiable.

### Black areas disappear
Inspect Opaque versus Masked/Translucent, the explicit opacity map and base-color alpha. Black RGB is not automatically transparent. Compare an exported RGBA image over a checkerboard. If the issue persists, provide the original texture including alpha and the affected material settings.

### UV seams or inverted details
Inspect texture padding, mip/filtering behavior, UDIM assignment, source channels and normal convention. Disable vertex color for a texture-only comparison. State which NPR style or renderer shows the seam and whether it is also present in an exported image.

### Slow navigation or incomplete path-tracing initialization
Wait for imports, then try a small known scene in the same renderer. Reduce additional preview size/update rate and inspect texture/geometry size. Compare Realtime with Progressive; include GPU model, driver, VRAM and scene size in a report. Do not infer that another user's GPU behaves like the reference RTX 4060.

### Render differs from viewport
Confirm camera, crop, renderer/backend, viewport versus offline workflow, scene/camera post override and output format. EXR linear appearance differs from display PNG. Warmup and samples affect temporal effects; backdrop inclusion and alpha affect the background. Check actual output files rather than only a screenshot of the viewport.

### Missing controls or unexpected selection
Select the relevant object/material slot and renderer. Filters may hide Outliner entries without hiding objects. A locked camera cannot be transformed until unlocked. Specialized presets expose only their supported controls. Restore the layout if a panel is off-screen; this need not reset scene data.

### Useful bug report
Include the build number, Windows/GPU/driver, exact steps from a fresh or supplied project, expected versus observed behavior, selected renderer/output route and a small screenshot or exported frame. Attach a minimal project and the required source texture if you are permitted to share them. Include the latest relevant log from the application's Saved/Logs directory. Remove personal paths or unrelated private data before posting publicly.

This manual documents functionality, not a promise that every third-party shader, model or codec behaves identically in every renderer. Preserve the distribution's third-party notices. The purchase/license terms on the product page govern seats and commercial use; the manual does not replace those terms. Use the support links accompanying your download for build-specific assistance.