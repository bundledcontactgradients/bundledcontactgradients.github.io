# Bundled Contact Gradients — project page

Source for <https://bundledcontactgradients.github.io>, the public project page for

> **Bundled Contact Gradients: Stabilizing Differentiable Simulation for Deployable Dynamic Tasks**
> Dyuman Aditya, Jin Cheng, Clemens Schwarke, Quan Nguyen, Gaurav Sukhatme,
> Marco Hutter, Stelian Coros, Gabriele Fadini

## The two copies of this page

There are two project pages, and only this one carries the author names: 

| | |
| --- | --- |
| <https://bundledcontactgradients.github.io> | this repo — named authors, affiliations, institution logos |
| <https://bundledcontacts.github.io> | the anonymous copy sent to reviewers — no names, affiliations, logos or personal links anywhere in the repo |

The bare anonymous URL is what goes in the submitted paper; this one is for sharing
publicly. When the content below changes, apply the same change to both repos — the
anonymous copy differs only in the hero's author block (and its `static/images/logos/`
and `tools/build_logos.py`, which it does not have). Keep the anonymous copy free of
names until the review process is over.

## Filling in the results

Every result slot on the page is currently a dashed **placeholder box** that names the
file it expects, e.g. `static/videos/sim_run.mp4`. To go live, drop the file in and
replace the whole `<div class="media-placeholder ...">` with:

```html
<!-- video -->
<video class="result-media" autoplay muted loop playsinline preload="metadata"
       poster="./static/images/sim_run_poster.jpg">
  <source src="./static/videos/sim_run.mp4" type="video/mp4">
</video>

<!-- figure -->
<img class="result-media" src="./static/images/learning_curves.png" alt="Learning curves.">
```

### Expected media

| File | Section |
| --- | --- |
| `static/videos/teaser.mp4` | Teaser — hardware montage of all four motions |
| `static/videos/supplementary.mp4` | Supplementary video |
| `static/videos/sim_{run,jump,fight,dance}.mp4` | Learned motions in simulation |
| `static/videos/real_{run,jump,fight,dance}.mp4` | Zero-shot sim-to-real transfer |
| `static/videos/compare_{bcg,shac,ppo}.mp4` | Comparisons after transfer to MuJoCo |
| `static/images/method_overview.png` | Method overview (paper Fig. 2) |
| `static/images/gradient_variance.png` | Policy-gradient variance (paper Fig. 3) |
| `static/images/gradient_averaging.png` | Contact-local gradient averaging (paper Fig. 4) |
| `static/images/learning_curves.png` | Learning curves (paper Fig. 5) |

Encode videos as H.264 MP4 (`-movflags +faststart`), muted and loop-friendly; keep each
one small enough for a snappy page (roughly ≤ 10 MB) and add a poster frame for the ones
that are not set to autoplay.

### The paper PDF

The PDF is not hosted here while the paper is under review, so the header's *Paper*
button is disabled. To enable it, drop the PDF at
`static/pdfs/bundled_contact_gradients.pdf` and follow the comment above that button in
`index.html`. Only the anonymized PDF may go in the anonymous repo, and its metadata
has to be checked first (`pdfinfo` — Author/Creator must not name anyone).

### Still to fill in

The **Training parameters** section is the "other training parameters are listed on the
website" reference from the paper. Rows tagged `TBD` still need real values.

## Local preview

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```

## Website license

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.

It is based on the [Nerfies project page](https://github.com/nerfies/nerfies.github.io).
