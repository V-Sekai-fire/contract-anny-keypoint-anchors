# contract-anny-keypoint-anchors

Where the COCO-WholeBody keypoints sit on ANNY's base mesh, as vertex weights, checked against the data.

## What it is for

ANNY's keypoint regressor turns vertices into named keypoints by a linear blend, and ships weights only for the body and feet. This repository builds the face and hand weights on the same mesh, merges them with ANNY's own by label into the regressor's file format, and keeps the label order, links and colours as the wire format a pose control is drawn in. A weight vector indexes one topology, so every file records the mesh it was built on and the check fails on a mismatch.

## Build and check

```sh
python build_wholebody_anchors.py
python check_keypoint_anchors.py
```

The check re-derives each claim from the installed ANNY package, and its self-test runs negative controls that must fail.

## Licence

Apache-2.0 OR MIT, at your option; see `LICENSE-APACHE` and `LICENSE-MIT`. The body and feet weights derive from ANNY's own, which is Apache-2.0, and `CITATION.cff` names the sources.
