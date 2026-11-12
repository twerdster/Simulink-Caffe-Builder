# Simulink-Caffe-Builder context

## Purpose

2015 Simulink experiment whose embedded MATLAB functions write Caffe layer configuration text, not neural-network execution.

## Implementation evidence

The tracked models contain layer text writers. The collateFiles.m stage mentioned by the original instructions is absent from the Git tree.

Key entry points: `CaffeLibrary.mdl`, `Example_3Stage.mdl`.

## Documentation state

The README explains operations, requirements, validation scope and limitations. Its pre-existing explanatory SVG is retained and labeled as a schematic rather than a runtime result. Source files and attribution are unchanged.

## Validation scope

Model text and embedded function inspection only; no current MATLAB load/simulation, Caffe parse, numerical execution or training. No automated suite or saved validation log.

## Limitations

Missing collation script, subset of historical layers, unverified current model compatibility and embedded function/mask inconsistencies. Files can be overwritten.
