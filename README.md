# boltz2-visual

Interactive architecture flow for **Boltz-2** (protein + ligand → structure + affinity).

Live: https://goknurarican.github.io/boltz2-visual/

Single-file HTML (SVG + vanilla JS). Configure `N_prot`, `N_lig`, `S`, toggle `affinity`, hit **Play** to step through the pipeline — trunk, diffusion, confidence, and (when affinity is on) the second `Boltz2.forward` pass that reloads `boltz2_aff.ckpt` (`main.py:1336` / `main.py:1406`) and re-runs `AtomDiffusion.sample()` before the `AffinityModule` heads.

Each step shows the tensor transformation in the side panel: inputs, operator, and output rendered as 1D / 2D / 3D / 4D grids with shapes.
