# Simulink-Caffe-Builder maintenance workflow

Read `SUMMARY.md`, this file and `README.md` before editing.

## Working on the repository

Use MATLAB/Simulink only in a separately scoped runtime validation. Review signatures, masks and graph names before attempting export. Keep the absent collation stage explicit in prose and visuals; do not imply complete prototxt generation or numerical training.

## Documentation checks

- Check claims against the named source files and recorded results. Separate source inspection,
  configuration generation, runtime execution and benchmark evidence.
- Keep README setup requirements available without following an advanced guide. Check Markdown
  headings, links and image references, including source files omitted by a sparse checkout.
- Inspect labels inside diagrams as well as captions. Never turn a schematic or generated input
  into an implied successful run.
- Keep original source, credits and license notices intact for documentation-only changes.
- Review and synchronize `SUMMARY.md` and `SKILL.md` before every commit. Record any unrun checks
  as limitations rather than implying that validation passed.

## Current evidence boundary

Model text and embedded function inspection only; no current MATLAB load/simulation, Caffe parse, numerical execution or training. No automated suite or saved validation log.

Missing collation script, subset of historical layers, unverified current model compatibility and embedded function/mask inconsistencies. Files can be overwritten.
