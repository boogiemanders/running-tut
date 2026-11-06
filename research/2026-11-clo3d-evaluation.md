# CLO 3D for Running Tut: should we use it, and can Claude drive it?

_Researched 2026-11-06. Prices in USD, before tax. Check the vendor pages before buying; prices move._

## Short answer

- **Yes, CLO is the right tool to try first.** It is the industry standard for 3D garment design, an Individual license costs $50/month (or $450/year), and it covers exactly what we need: draw 2D patterns, sew them onto an avatar, simulate real fabrics, and render images and turntable videos good enough for Tut's concept videos.
- **Yes, Claude can partly control it**, through CLO's built-in Python API, running on Anders's computer. That works well for repeatable jobs (swap fabrics and colorways, export renders, pattern DXFs and tech packs, batch variations). It does **not** replace a human designing the garment by hand. Drawing and fitting a new pocket or gel-loop pattern is still visual, hands-on work in the CLO window.

## What CLO does

CLO 3D (by CLO Virtual Fashion, the same company that makes Marvelous Designer) is pattern-based 3D clothing software:

- **2D pattern window + 3D avatar window.** You draft flat pattern pieces, sew them, and the garment drapes on an avatar using physics simulation.
- **Real fabric physics.** Stretch, weight and bend settings, so a phone pocket on a pant leg will sag or bounce realistically. Useful for checking pocket placement before cutting fabric.
- **Trims and details.** Zippers, elastics, topstitching, bonding, and pockets are all supported, so gel loops (small elastic loops) can be modeled.
- **Colorways.** One garment, many color and fabric variants.
- **Rendering and animation.** Photo-quality stills, turntables, and the avatar walking or running. Good material for concept videos.
- **Manufacturing hand-off.** Exports pattern files (DXF, the format factories use), tech packs, and 3D files (OBJ, FBX, glTF, USD).

## Pricing and licenses

| License | Price | Who it is for |
|---|---|---|
| Student | $25/mo or $225/yr | Students learning |
| **Individual** | **$50/mo or $450/yr** | Freelancers and one-person businesses |
| Enterprise | Custom quote | "Any company with 2+ employees" |

Source: [CLO pricing](https://www.clo3d.com/en/pricing), [How much does CLO cost](https://support.clo3d.com/hc/en-us/articles/115012815487-How-much-does-CLO-cost). There is a free trial ("Start for free"); length not stated on the page.

**Watch out:** CLO says Enterprise is for companies with 2+ employees, and that trial users signing up with a company email usually get pushed to Enterprise. Running Tut is two founders. Practical path: one of you (whoever designs) buys an Individual license in your own name while it is just side work, and revisit if Running Tut becomes a company with staff. Worth a quick email to CLO sales to confirm before paying annually.

## Learning curve

- Plan on **2 to 4 weeks** of evenings to get comfortable, and a couple of months to be fast. The hard part is not the software, it is **pattern-making**: CLO assumes you understand how flat pieces become a garment.
- Good news: CLO has a large free tutorial library (CLO's own YouTube channel and the CLO-SET Academy) and a big community, because it is the most used tool in fashion schools.
- Shortcut: start from an existing pant or tee pattern (CLO ships samples, and pattern files can be bought or commissioned) and modify pockets and loops, rather than drafting from zero.

## Alternatives

| Tool | Price | Fit for us |
|---|---|---|
| **CLO 3D** | $50/mo Individual | Best fit. Standard in industry, manufacturers recognise its files, best learning resources, has a Python API. |
| **Browzwear (VStitcher)** | Enterprise-only, quote-based; indie program by application | Strong for technical fit and big sportswear brands, but no self-serve individual license. Overkill now. |
| **Marvelous Designer** | Subscription; an "Indie" tier was added in 2026 (price on request, for low revenue) | Same physics engine as CLO, but aimed at games/film. Weaker on manufacturing output (tech packs, grading). Pick CLO instead. |
| **Style3D Studio** | Quote-based; markets itself as cheaper than CLO | Capable and growing, strong in Asian supply chains. Smaller English-language community. A fallback if CLO's licensing is a problem. |

Sources: [Delogue comparison](https://www.delogue.com/blog/clo3d-vs-browzwear-vs-optitex-vs-style3d-3d-fashion-software) (2021–23, prices may be stale), [Marvelous Designer indie pricing](https://digitalproduction.com/2026/01/12/marvelous-designer-adds-indie-pricing-quietly/).

## Does it suit a two-person premium running brand?

Yes, with the right expectations:

- **Fits the launch plan.** Tut makes concept videos, we see what gets traction, then prototype. CLO renders let Tut show realistic designs (pockets, gel loops, colorways) in videos *before* any sample is sewn. Cheap way to test ideas.
- **Saves sample rounds.** Fit and pocket placement can be checked in 3D, cutting the number of physical prototypes. Samples often cost roughly $100–500+ each at a factory (rough estimate, not sourced), so this pays for the license quickly.
- **Speaks factory.** When we reach a manufacturer, CLO DXF patterns and tech packs are formats they already use.
- **Limits.** Simulation is close but not perfect for technical stretch fabrics; you still need at least one physical sample before production. And someone has to learn pattern-making basics, or we hire a freelance CLO pattern maker for the first base patterns (common on Upwork; rates vary, roughly $30–80/hr is a guess).

## Can Claude control CLO?

### What exists

- **Official CLO API / SDK** ([developer.clo3d.com](https://developer.clo3d.com/)): a C++ plug-in SDK and a **Python Script API** that runs *inside* CLO (Edit > Python Script > Run Python Script, or drag a `.py` file onto the CLO window). Current SDK: v11.0.1 for CLO 2026.1, Windows and Mac.
- API modules include **Import, Export, Fabric, Pattern, Utility** and a REST API. Export functions cover OBJ, glTF, FBX, USD, DXF patterns, tech packs, snapshots, rendered images and turntable videos. Fabric functions can add, replace, and assign fabrics to pattern pieces. Documented scenarios include auto-hanging, simulation, rendering, colorways and animation renders.
- **A third-party MCP connector** ([clo3d-mcp by Ubani-Studio](https://glama.ai/mcp/servers/Ubani-Studio/clo3d-mcp/tree), MIT license): a script you run inside CLO, plus an MCP server that Claude Code talks to. It exposes 46 tools (scene, patterns, fabrics, import/export, simulation, colorways). It is a small hobby project, not from CLO, so treat it as experimental.
- Not clearly stated: whether the API needs an Enterprise license. The docs and the MCP project don't say it is restricted; confirm during the free trial.

### What is realistic

How it would run: Anders installs CLO on his computer, we start a **Remote Control session** (Claude Code running on that machine), and Claude either writes and runs CLO Python scripts or uses the MCP connector. CLO has to be open; this is not a cloud service.

| Task | Feasible? |
|---|---|
| Generate 20 colorways of a design and render each one | **Yes.** The API's sweet spot. |
| Batch-export renders, turntables, DXF patterns, tech packs | **Yes.** |
| Swap fabrics (e.g. try 3 fabric weights on the same pant) | **Yes.** |
| Tweak a known measurement (move a pocket 2 cm, lengthen an inseam) | **Probably**, via pattern functions, but fiddly; needs testing. |
| Design a brand-new garment from a text description | **No, not reliably.** Pattern drafting is visual, iterative work. A person should do it, with Claude helping on research and specs. |
| Judge whether a drape "looks right" | **Partly.** Claude can look at rendered images and give feedback, but final calls are yours. |

Computer-use (Claude clicking around the CLO interface) is also possible but slow and error-prone for a dense 3D app; scripting is the better route.

## Recommended next steps

1. Start the CLO free trial on Anders's computer with a personal email; confirm the Python Script menu is available on the Individual license.
2. Build one hero piece first: the **full-length running pant with phone pockets and gel loops**, starting from a stock pant pattern.
3. Once a base pattern exists, have Claude (via Remote Control) script colorway and fabric variations plus renders for Tut's concept videos.
4. Buy the Individual license ($450/yr saves 25%) only once the trial shows you'll actually use it.
