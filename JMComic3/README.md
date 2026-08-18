# JMComic3 ad-removal patch

## Verified behavior from prior testing

- App opened directly to the home page without the previous close-X gate.
- Ads were absent from the tested pages.
- Comic reading remained functional.
- Known minor regression: returning from Personal Center to Home may require selecting the content line again.

## What is still missing

The exact patch recipe/source changes have not yet been recovered into this repository. The prior patched APK itself is not a suitable source-of-truth for a public archive.

When the recipe is recovered, record:
- target APK version and SHA-256
- exact resource/smali changes
- rebuild command/tool versions
- signing method
- post-patch validation checklist
- compatibility result after any upstream data-package or APK update

Do not publish the proprietary APK binary here as a substitute for reproducible patch source.
