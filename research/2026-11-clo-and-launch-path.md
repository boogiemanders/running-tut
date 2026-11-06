# CLO 3D, and the video → prototype → manufacturer plan

Researched 2026-11-06 for Running Tut, following Anders's questions: could we design in CLO, could Claude control it, and does this launch plan hold up? Tut makes videos about his ideas → see what gets traction → prototype the winners → adjust → make pieces ourselves → move to a manufacturer.

## Short answers

- **CLO is worth a trial.** It's the standard 3D garment tool, $50 a month for an individual licence. It lets Tut design a pant digitally, check pocket placement on a moving avatar, export patterns a sample maker can sew from, and make renders for videos before sewing anything.
- **Claude can help with CLO but can't be the designer.** CLO's Python scripts run inside the open app and can export patterns, tech packs, renders and turntable videos, and swap fabrics and colourways. No API for drawing or editing pattern pieces was confirmed. On Anders's Mac, Claude could also click through CLO with computer use, but that is slow and fragile for real pattern work. Realistic split: **Tut (or a freelance CLO patternmaker) drafts the garment; Claude automates the repetitive output** (colourway renders, tech-pack exports, turntables for videos, spec sheets, factory emails).
- **The plan is sound, with one change.** Testing ideas with videos first is exactly Hormozi's "content first, product second." The weak step is "make it ourselves": stretch technical fabric needs coverstitch and flatlock machines and a lot of skill, and home-sewn pieces would undercut "luxury that lasts." Self-sew for rough prototypes only; use a small-batch sample studio for anything sold.

---

## 1. CLO 3D

**Price** (clo3d.com/pricing and CLO support FAQ, checked 2026-11-06):

| Licence | Monthly | Yearly |
|---|---|---|
| Individual | $50 | $450 |
| Student | $25 | $225 (50% off) |
| Business / Academic | quote | quote |

The pricing page says "start for free." A comparison site says the trial is 14 days; CLO's own pages didn't confirm the length.

**What it does that matters for us** (from CLO and comparison sites; the comparison sites sell competing tools, so treat them carefully):
- 2D pattern making linked to 3D simulation on avatars, with fabric physics, so you can see drape, stretch and where a loaded pocket sits.
- Exports DXF patterns (the format sample makers and factories use), tech packs, BOMs, OBJ/GLB 3D files, render images, turntable and animation videos.
- Usually described as the easier on-ramp than Browzwear. Small pattern details still take time to learn. CLO has free tutorials and CLO Academy courses.

**Mac:** Anders's laptop is an Apple-silicon MacBook Air. CLO runs on macOS, but heavy simulation on a MacBook Air will be slow. One user comment on CLO's support site says Python scripting is "only Windows feature." That's unconfirmed, so test it during the trial.

**What Claude can control** (CLO developer docs, developer.clo3d.com):
- Scripts run *inside* the open CLO app (Edit > Python Script, or drag a `.py` file onto the window). There is no standalone command line.
- **Confirmed scriptable:** export (`ExportDXF`, `ExportTechPack`, `ExportRenderingImage`, `ExportTurntableVideo`, `ExportOBJ`, `ExportGLTF`, `ExportBOM`, colourway renders), fabrics (`AddFabric`, `ReplaceFabric`, `AssignFabricToPattern`), colourway and avatar lookups, and simple pop-up dialogs.
- **Not confirmed:** creating or editing pattern pieces and running the simulation. The pattern section of the API list couldn't be read in full, so check it during the trial.

**Alternatives** (all have trials): Marvelous Designer (same parent company, cheaper, built for games and film, weaker for production patterns), Browzwear (production-focused, steeper learning curve), Style3D (cheaper, aggressive marketing). For a brand that has to hand patterns to a factory, CLO is the safe default.

**How CLO fits the plan:** Tut can make videos from CLO renders and turntables of a concept *before* paying for a single sample. Then only the winning concepts get sewn. That turns step 1 from "talk about an idea" into "show the idea," which should get a clearer signal.

## 2. Testing ideas with videos

This is the cheapest test of demand, and it follows Hormozi's lead-gen order (content before ads). Make it measurable:

- **One idea per video.** Example: "full-length run pant that fits a Pro Max and 6 gels." Show the CLO render, a sketch or a mock-up.
- **Measure intent, not views.** Count saves, shares, "where can I buy this" comments, and especially **waitlist sign-ups** from a link in the bio. Decide the bar before posting, e.g. a concept goes to prototype once it gets 100+ waitlist sign-ups or clearly beats the other concepts on saves.
- **Ask in the video.** "Would you run in this? What would you carry?" The comments double as the customer interviews the earlier report recommends.
- **Post where runners are.** Instagram and TikTok, plus local run-club group chats (warm outreach).

## 3. Prototyping

Costs and timing (Maker's Row and LA sample studios; these are marketing pages, so treat them as ballpark):

| Step | Cost | Time |
|---|---|---|
| Tech pack | $0 (DIY; CLO can export one) to ~$300 | days |
| Pattern making | $150 to $550 per design | 1 to 2 weeks |
| Sample | $50 to $400 per garment per round | 2 to 4 weeks per round |
| Rounds needed | 2 to 3 is typical | — |
| Full development, joggers-type pant (LA studio) | from ~$1,500 per style | 4 to 8 weeks |

**Studios to contact** (directory listings, so prices and fit need checking):
- **TFSN Studio**, Pasadena: lists activewear including flatlock pieces; 1 to 10 protos and samples, 500+ production.
- **Clothier Design Source**, St. Paul, MN: listed for athletic wear, 2 to 4 sample rounds.
- **Avoid:** p.LAB (NYC) says it can't make athletic wear. Bomme (LA) only takes full collections, not single styles.

**Founder example:** Cause I Run (activewear, 2016) used a local patternmaker and one sample round. The tank needed no changes and the pants needed a small leg-opening tweak, but the sports bra took months. They then funded production on Kickstarter.

## 4. "Make it ourselves," then the manufacturer

- **Making it ourselves:** fine for rough prototypes to test pocket placement on a run. For pieces we sell, stretch fabric needs a serger, a coverstitch and ideally a flatlock machine, plus skill. Durability is the whole brand promise, so home-sewn stock is risky. A better middle step is **small-batch cut-and-sew at 50 to 100 units** ($15 to $45 per unit sewing cost in the US, according to Maker's Row), funded by preorders from the waitlist.
- **Manufacturer:** full custom typically needs 300 to 500 units per style per colour, and custom fabric or dye about 500 per colour. US and Mexico sewing (CMT) minimums are about 150 to 300 per colour; Asia full-package about 600+. Expect a 30 to 50% deposit and 30 to 45 days after sample approval.

## Suggested sequence

1. Start the CLO trial; Tut models 3 concepts (e.g. the pant, a short, a top).
2. Post one video per concept over 2 to 3 weeks, each with a waitlist link.
3. Take the winner to a sample studio (budget ~$1,500 to $2,500 and 6 to 10 weeks for 2 to 3 rounds).
4. Wear-test the sample on long runs; film it (proof content for the guarantee).
5. Open preorders to the waitlist; run 50 to 100 units small-batch.
6. Move to a manufacturer at 300+ units once reorders and preorders justify it.

## Sources

- CLO pricing: https://clo3d.com/pricing
- CLO licence FAQ: https://support.clo3d.com/hc/en-us/articles/115012815487
- CLO Python API: https://developer.clo3d.com/python.html
- CLO API list: https://developer.clo3d.com/list.html
- CLO GUI API: https://developer.clo3d.com/gui_api.html
- CLO support, Python script article: https://support.clo3d.com/hc/en-us/articles/115014409267
- CLO forum, automating pattern changes: https://support.clo3d.com/hc/es/community/posts/4959333294361-Automating-pattern-changes
- WearView (competitor), CLO vs Browzwear (May 2026): https://www.wearview.co/blog/clo3d-vs-browzwear
- WearView (competitor), CLO vs Marvelous Designer (2026): https://www.wearview.co/blog/clo3d-vs-marvelous-designer
- WearView (competitor), CLO alternatives (May 2026): https://www.wearview.co/alternatives/clo3d-alternatives
- Maker's Row, sample budget: https://makersrow.com/blog/developing-a-product-use-this-real-sample-budget-as-a-guide/
- Maker's Row, manufacturers that make samples (2026): https://makersrow.com/blog/clothing-manufacturer-that-makes-samples/
- Maker's Row, starting with no money (2026): https://makersrow.com/?p=51711
- Maker's Row, Cause I Run (2016): https://makersrow.com/?p=16416
- Bomme Studio, sample making: https://www.bommestudio.com/sample-making-services
- Bomme Studio, women's activewear SKU plan: https://www.bommestudio.com/blog/sample-sku-plan-womens-activewear
- CFDA directory, TFSN Studio: https://cfda.com/production-directory/tfsn-studio
- p.LAB / Brooklyn Fashion Accelerator, cut & sew: https://bkaccelerator.com/make/cut-sew/
