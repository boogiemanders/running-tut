# CLO 3D feature guide: what each function does and how to use it

_Written 2026-11-06 from CLO's public manual and tutorials. Menu names follow recent CLO versions (2024–2026) and can shift slightly between releases. When something doesn't match, search the [CLO Online Manual](https://support.clo3d.com/hc/en-us/categories/115000184108) for the tool name. The last column lists a free or open-source tool that does a similar job._

## How CLO is laid out

- **3D window (left):** the avatar and the draped garment.
- **2D Pattern window (right):** flat pattern pieces, like a paper pattern on a table.
- **Library (far left):** avatars, fabrics, trims, hardware, sample garments.
- **Object Browser / Property Editor (right):** lists everything in the scene, and settings for whatever you've selected.
- **Simulate button (spacebar):** turns physics on and off. Drafting is done with it off; draping happens with it on.

Most work is a loop: **draw in 2D → arrange on avatar in 3D → sew → simulate → adjust in 2D → repeat.**

---

## 1. Avatars (the body)

| What | How in CLO | Free alternative |
|---|---|---|
| Load a body | Library > Avatar, double-click a male/female avatar. | MakeHuman (free, exports to Blender) |
| Change size and proportions | Avatar > Avatar Editor. Type measurements (height, waist, hip, inseam, thigh). | MakeHuman sliders |
| Set a pose | Library > Avatar > Pose, double-click a pose (a running stride works for checking pockets). | Blender + Mixamo poses |
| Fit points / arrangement points | Show Avatar > Show Arrangement Points (blue dots). Used to snap patterns around the body. | Manual placement in Blender |
| Import your own body scan | File > Import > OBJ/FBX, then set it as an avatar. | Blender |

**For us:** set the avatar to runner measurements and use a mid-stride pose to see how a phone pocket swings.

## 2. Pattern drafting (2D)

| What | How in CLO | Free alternative |
|---|---|---|
| Draw a rectangle/circle piece | 2D toolbar > Rectangle (or Circle), click-drag in the 2D window. | Seamly2D / Valentina |
| Draw any shape | Polygon tool: click points, double-click to close. Hold-drag to make curves. | Seamly2D |
| Edit points/lines | Edit Pattern tool (Z): drag points; Edit Curvature (C) to bend lines; Add Point (X). | Seamly2D |
| Exact measurements | Right-click a point/line > Move by Distance, or type length in Property Editor. Grid and ruler on top. | Seamly2D (fully formula-based) |
| Darts | Dart tool: draw inside a piece. | Seamly2D |
| Internal lines (fold, pocket placement) | Internal Polygon/Line tool. Mark pocket openings and gel-loop positions here. | Seamly2D |
| Mirror / symmetric pieces | Right-click piece > Clone as Symmetric Pattern (edits both sides at once). | Seamly2D "mirror" |
| Seam allowance | Select piece > Seam Allowance tool, set width (e.g. 1 cm). | Seamly2D |
| Notches | Notch tool, click on an edge. | Seamly2D |
| Start from a template | Library > Garment, or File > Open a sample .zprj and modify it. | FreeSewing.org (free parametric patterns, incl. joggers/leggings) |
| Import a paper/CAD pattern | File > Import > DXF (AAMA/ASTM). | Seamly2D, Inkscape |

**For us:** don't draft a pant from zero. Open a sample pant or import a FreeSewing pant DXF, then add pocket pieces and loops.

## 3. Arranging and sewing

| What | How in CLO | Free alternative |
|---|---|---|
| Place pieces around the body | In 3D, click a piece then click an arrangement point; or right-click > Reset 2D Arrangement. | Blender (move pieces manually) |
| Segment sewing (edge to edge) | Segment Sewing tool (N): click one edge, then the matching edge. | Blender "Sewing" springs |
| Free sewing (part of an edge) | Free Sewing tool (M): click start/end on each side. Used for pockets sewn onto a panel. | Blender |
| Check sewing | Sewing lines show as colored pairs; mismatched lengths show in the Property Editor. | n/a |

## 4. Simulation and fit

| What | How in CLO | Free alternative |
|---|---|---|
| Drape the garment | Press Simulate (spacebar). Garment falls onto the avatar. | Blender Cloth modifier |
| Grab and pull fabric | With simulation on, click-drag cloth in 3D. | Blender |
| Fit Map / strain | 3D window toolbar > Fit Map (Strain or Stress). Red = tight. | Not really available free |
| Pressure points | Fit map shows where the garment presses on the body. | No |
| Garment fit check while moving | Animation mode (see §9), play a running motion. | Blender + Mixamo run cycle |
| Layering | Select piece > Property Editor > Layer (0, 1, 2…). Higher layer sits on top (e.g. pocket over pant). | Blender collision |
| Particle distance (accuracy) | Property Editor > Particle Distance. Lower (5 mm) = more detail, slower. Use 20 mm while drafting. | Blender quality steps |

**For us:** Fit Map plus a run animation is how we'd test that a loaded phone pocket doesn't sag or pull the waistband.

## 5. Fabrics

| What | How in CLO | Free alternative |
|---|---|---|
| Apply fabric | Drag a fabric from Library > Fabric onto a piece, or Object Browser > Fabric > Add, then assign. | Blender materials |
| Physical properties | Property Editor > Physical Property > Preset (e.g. "Jersey", "Spandex"). Or set stretch weft/warp, bending, weight, thickness. | Blender cloth settings (stiffness, mass) |
| Measure a real fabric | CLO Fabric Kit (paid hardware) or ask the mill for a CLO fabric file (.zfab). | Approximate by hand |
| Texture / print | Property Editor > Texture: load an image; adjust scale and angle. | Blender, GIMP |
| Normal / bump maps (knit look) | Property Editor > Normal Map. | Blender |
| Substance materials | Import .sbsar files. | Blender + free textures (ambientCG) |
| Reflectivity / sheen | Material type (Fabric, Leather, Metal, Glossy). | Blender |

## 6. Trims, hardware and details

| What | How in CLO | Free alternative |
|---|---|---|
| Zippers | Zipper tool: draw along two edges; choose puller/slider in Library. | Blender model |
| Elastic | Select a line > Property Editor > Elastic: on, set ratio (e.g. 80%). Use for waistband and **gel loops**. | Blender |
| Topstitching | Topstitch tool: click an edge; set stitch type and thread color. | Blender texture |
| Buttons, snaps, eyelets | Button / Buttonhole tools; hardware from Library. | Blender |
| Trims (aglets, logos, tabs) | File > Import > OBJ as trim, then Trim tool to attach. | Blender |
| Puckering, bonding, tape | Puckering in Property Editor; Bonding/Skiving tool for taped seams. | No |
| Graphics / logos | Graphic tool: drop a PNG/AI onto a piece; set print, embossed, or reflective. | Blender decals |
| Folding / pleats | Fold Arrangement tool; Fold Angle on internal lines. | Blender |

**For us:** gel loop = a small rectangle piece sewn at both ends on an internal line, with elastic on. Reflective logos via the Graphic tool.

## 7. Colorways

| What | How in CLO | Free alternative |
|---|---|---|
| Make color variants | Object Browser > Colorway tab > Add. Each colorway keeps its own fabric colors, prints, trims. | Blender scenes/materials |
| Switch between colorways | Click the colorway thumbnail. | Blender |
| Render all colorways | Render > Render settings > "All colorways". | Blender script |
| Pantone/color libraries | Color Picker > Pantone, or CLO's color libraries. | Free hex/Pantone lookups |

**For us:** fast way to show Tut's audience 4–6 restrained colorways and let comments vote.

## 8. Rendering (images)

| What | How in CLO | Free alternative |
|---|---|---|
| Quick snapshot | File > Snapshot > 3D Window (PNG). | Blender viewport render |
| Photo-real render | Render > Render (or the Render window). Set image size, camera views, background, quality. | Blender Cycles |
| Lighting / HDRI | Render Property > Environment: pick an HDRI and lights. | Blender + Poly Haven HDRIs |
| Multiple views | Render > Image > choose Front/Back/Left/Right. | Blender cameras |
| Turntable video | Render > Turntable: set frames and degrees. | Blender |

## 9. Animation

| What | How in CLO | Free alternative |
|---|---|---|
| Enter animation mode | Top-right mode dropdown > Animation. | Blender timeline |
| Apply a motion | Library > Avatar > Motion (walk/run), or import FBX/BVH from Mixamo. | Mixamo (free) + Blender |
| Record cloth simulation | Press Record; CLO simulates the garment through the motion. | Blender bake cloth |
| Export video | Render > Animation Video (MP4). | Blender |

**For us:** a 5-second run-cycle clip of the pant is ideal for Tut's concept videos.

## 10. Measuring and grading

| What | How in CLO | Free alternative |
|---|---|---|
| Measure garment | 2D: Pattern Measure tools (circumference, length). 3D: Garment Measure tools. | Seamly2D measurements |
| Grading (sizes S–XL) | Grading tool: create size table, set grade rules per point. | Seamly2D (measurement files per size) |
| Size switching | Choose size from the grading list; garment updates. | Seamly2D |

## 11. Tech packs and production files

| What | How in CLO | Free alternative |
|---|---|---|
| Tech pack | File > Export > Tech Pack (or Tech Pack mode). Add callouts, measurement table, BOM (fabrics, trims). | Google Sheets template + rendered images |
| Pattern files for factory | File > Export > DXF (AAMA/ASTM) or Pattern (PLT/ PDF for printing). | Seamly2D DXF export |
| Print a pattern at home | File > Export > PDF (tiled). | Seamly2D tiled PDF |
| 3D files | File > Export > OBJ / FBX / glTF / USD / Alembic. | Blender |
| Share online | CLO-SET (CLO's cloud platform) for comments and review. | Google Drive + renders |

## 12. Files to know

- **.zprj**: full CLO project (avatar + garment + settings). The one to save and share.
- **.zpac**: garment only.
- **.zfab**: a fabric with its physics.
- **.avt / .avs**: avatar and avatar size.
- **.dxf**: industry pattern file for factories.

## 13. Scripting and automation

- Edit > Python Script > Run Python Script, or drag a `.py` onto the window.
- The public API ([developer.clo3d.com](https://developer.clo3d.com/)) covers import, export, fabrics, patterns, colorways and rendering. Good for batch jobs like "render every colorway from four angles."
- This is how Claude would work with CLO on Anders's computer (see [CLO evaluation](./2026-11-clo3d-evaluation.md)).

## A free-only route, if we skip CLO

1. **Pattern:** FreeSewing.org base pattern → edit in **Seamly2D** (add pockets, loops).
2. **3D:** body from **MakeHuman**, garment pieces into **Blender**, sew with cloth "sewing springs", simulate with the Cloth modifier, run cycle from **Mixamo**.
3. **Render:** Blender Cycles with Poly Haven HDRIs.
4. **Factory files:** Seamly2D DXF + a Google Sheets tech pack.

This costs nothing but is **much** slower and fiddlier than CLO, and Blender cloth isn't fabric-accurate. Fine for rough concept visuals; for fit and factory hand-off, CLO is worth the $50/month.

## Learning order for the first month

1. Week 1: CLO's "Getting Started" tutorials; open a sample garment, change fabric and colors, render it.
2. Week 2: Modify a sample pant: move/resize a pocket, add a gel loop with elastic.
3. Week 3: Fit Map + run animation; export a short clip for Tut.
4. Week 4: Colorways and a basic tech pack.

Free learning: [CLO YouTube channel](https://www.youtube.com/@CLOVirtualFashion), [CLO Online Manual](https://support.clo3d.com/hc/en-us), CLO-SET Academy.
