# ISWAS v7

Optimized static build of **It Started With a Scream** for GitHub Pages.
Same pitch, same pages, same gallery. About 11 MB, down from about 34 MB in v6.3.
It no longer waits on the 3D room to show the dossier.

## Upload

1. Create a public repo named `ISWAS_v7` (or push these files onto `main`).
2. Upload **the contents of this folder** to the repository root. Include `.nojekyll`.
3. Settings → Pages → Deploy from branch → `main` → `/ (root)`.
4. The site will be at `https://jotsmedia.github.io/ISWAS_v7/`.

Paths are base-aware (`window.__ISWAS_BASE`), so a project-page subpath works.
A custom domain on the repo root also works.

## What changed for speed

- First paint is the prerendered page. The intro no longer blocks on WebGL (the old loader waited up to 12s for the lodge).
- The 1.1MB gallery bundle downloads after the page is up, not during first parse.
- Repeat visits in the same tab skip the intro.
- Textures, plates, portraits, and book covers are recompressed. Cutout props are WebP.
- Phones and Save-Data / slow connections load a smaller `m/` texture set.
- Unused normal maps and duplicate textures from v6.3 are not in this upload.
- Desktop and mobile: the dossier is readable immediately; the room fades in behind it.

Do not strip the NUL bytes inside the TanStack hydration payloads in the HTML files.
