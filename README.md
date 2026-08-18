# Android Ad Removal

Generic and non-LINE ad-removal research and reproducible APK patch recipes.

## Known project: JMComic3

Validated outcome from prior testing:
- app opens to the home page without the previous close-X gate
- ads removed from the tested pages
- comic reading remained functional
- known minor regression: returning from Personal Center to Home may require selecting the content line again

Do not use a redistributed proprietary patched APK as the source of truth. Preserve a reproducible recipe instead: target version/hash, modified resources/smali, rebuild steps, signing steps and post-patch validation.

## Generic tooling

- apktool / resource editing
- smali-level static patches
- network/ad-SDK disabling where appropriate
- rebuild and signature workflow
- version/hash gates so an app update does not silently receive an incompatible patch

## Update policy

When the upstream APK or remotely delivered data package changes, revalidate the relevant patch. Never claim compatibility solely because installation succeeds.
