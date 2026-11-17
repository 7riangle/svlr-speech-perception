# Scottish Vowel Length Rule: online perception experiment (portfolio demo)

A browser-based **BROOD–BREWED** identification task implemented in JavaScript and [jsPsych](https://www.jspsych.org/) for an undergraduate coursework project at the University of Edinburgh (2025). This repository contains a **shortened, non-research portfolio demonstration** prepared in 2026, not a completed perceptual study.

**[Open the project page](https://7riangle.github.io/svlr-speech-perception/)** · [Personal website](https://moses-im.netlify.app/)

> The GitHub Pages link will work only after this repository is published under the suggested name `svlr-speech-perception` and Pages has been enabled.

## Research question and design

The project asks whether Scottish English listeners would identify vowel-length differences between **brood** and **brewed** categorically or as context-dependent phonetic variation. It adapts the perception paradigm of Ferragne et al. (2011) and compares a carrier sentence and an additional sentence context.

The **proposed** experiment included a seven-step vowel-duration continuum (approximately 50–185 ms), with 20 repetitions per step in each context: **7 × 20 × 2 = 280 main trials**, plus headphone screening and practice trials. The proposed seven-step acoustic manipulation was **not produced and validated as seven distinct stimuli**, and no participant data were collected. The project must not be interpreted as evidence about Scottish listeners' actual perceptual categories.

## What the public demo implements

The demo illustrates the experiment workflow with a reduced number of trials:

| Part | Public demo |
| --- | ---: |
| Volume check | 1 |
| Anti-phase headphone screening | 6 (pass at least 5) |
| Practice | 2 (1 per context) |
| Main identification | 4 (2 per context) |

The two main stimulus WAVs are **representative, author-recorded placeholder tokens** that are replayed; the demo does **not** implement a seven-step duration continuum. It demonstrates audio preloading, presentation, randomisation, two-choice responses, response-time logging within the browser session, and 1–7 confidence judgements.

**Privacy:** No participant response data are saved to a file, stored on a server, or transmitted by application code. This is a portfolio demonstration, **not an invitation to participate in an approved research study**. There is no PHP backend or data-collection endpoint.

## Running locally

This project uses static HTML, JavaScript, and WAV files. A package manager or build process is not needed. jsPsych 8.2.2 and its plugins are loaded from the `unpkg.com` CDN, so an internet connection is required.

From this repository's root directory:

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000/`, then select **Try the experiment**. Use a desktop or laptop with stereo headphones or earphones. Audio should be served over HTTP(S), not opened directly as a `file://` page.

## Files

```text
index.html                 Project overview, design, caveats, references
demo/index.html            Demo introduction and trial counts
demo/original.html         Loads jsPsych and the experiment script
demo/brood_brewed.js       Demonstration sequence and responses
demo/audio/                Six third-party screening WAVs + two author recordings + generated beep
third_party/               Required attribution and BSD 2-Clause licence for screening WAVs
```

Only the two placeholder recordings actually used by the demo are included. The source ZIP contained seven numbered copies for each context; hashes confirmed that each set's seven copies was identical, rather than seven separate acoustic steps. Unused `booed.wav` and `noise_calib_stim.wav` are omitted.

The short volume-check `beep.wav` in this release was **regenerated as a 600 Hz sine tone** (0.55 seconds, with short fades) so its origin is clear; it does not reuse the source archive's beep.

## Third-party material and attribution

The six `antiphase_HC_*.wav` sound files used for the headphone check originate from the **McDermott Lab HeadphoneCheck** project, associated with Woods et al. (2017):

https://github.com/mcdermottLab/HeadphoneCheck

That project is published under the **BSD 2-Clause** licence. Its copyright notice, licence conditions and author list are reproduced in `third_party/HeadphoneCheck-LICENSE.txt` and `third_party/HeadphoneCheck-AUTHORS.txt`. These third-party sounds are **not** original work by Moses Im. The headphone-check logic here is separately implemented with jsPsych; it does not bundle McDermott Lab's `HeadphoneCheck.js` source file.

The six screening files were present in the supplied source ZIP. Before any further redistribution, the uploader should independently compare them with the upstream repository assets if an exact file-origin audit is needed.

The jsPsych library and plugins are loaded through an external CDN and are not copied into this repository.

## Selected references

- Ferragne, E., Bedoin, N., Boulenger, V., & Pellegrino, F. (2011). The perception of a derived contrast in Scottish English. *Proceedings of ICPhS XVII*, 667–670.
- Woods, K. J. P., Siegel, M. H., Traer, J., & McDermott, J. H. (2017). Headphone screening to facilitate web-based auditory experiments. *Attention, Perception, & Psychophysics, 79*, 2064–2072. https://doi.org/10.3758/s13414-017-1361-2

Other linguistic and prosodic references appear on the project overview page.

## Rights

The BSD 2-Clause licence in `third_party/` applies to the attributed McDermott Lab assets. No repository-wide open-source licence is asserted for this project's original text, code, or author-recorded audio.
