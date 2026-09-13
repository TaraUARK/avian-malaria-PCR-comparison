# Avian Malaria PCR Method Comparison

A self-contained, browser-based lab tool for planning, running, and reporting on a head-to-head comparison of three published avian malaria PCR detection methods, screened against an Actin (ACTB) DNA-quality control.

**Methods compared**
- **Hellgren nested PCR** — Hellgren, Waldenström & Bensch (2004), *Journal of Parasitology* 90(4):797–802
- **Drovetski three independent PCRs** — Drovetski et al. (2014), *Molecular Ecology* 23(13):3322–3329
- **Ciloglu one-step multiplex PCR** — Ciloglu, Ellis, Bernotienė, Valkiūnas & Bensch (2019), *Parasitology Research* 118(1):191–201

## Getting started

No install, no build step, no server, no account. Download **`Avian_Malaria_Methods_Comparison.html`** and open it in any modern desktop browser (Chrome, Firefox, Safari, Edge) — everything it needs (PDF generation, image processing) is bundled inline in that one file.

All data stays local to your browser. Nothing is uploaded anywhere.

## Workflow

1. **Step 1 — DNA Dilutions**: enter each sample's Bird ID and measured DNA concentration; the tool calculates the DNA and nuclease-free water volumes needed for a 25 ng/µL, 20 µL dilution, and flags samples too dilute to hit that target.
2. **Step 2 — Actin (ACTB) PCR**: a single run-once PCR verifying that each DNA extraction was successful, with its own master mix, thermocycler program, and expected product size.
3. **Step 3 — Hellgren Nested PCR**: Reaction 1 (universal, no gel — feeds Reactions 2a/2b), Reaction 2a (*Leucocytozoon*), and Reaction 2b (*Haemoproteus*/*Plasmodium*), each run in independent triplicate.
4. **Step 4 — Drovetski Three Independent PCRs**: three parallel reactions (UnivR1/UnivR2/UnivR3) sharing a forward primer, each run in triplicate.
5. **Step 5 — Ciloglu One-Step Multiplex PCR**: a single multiplex reaction run in triplicate, with genus identified by band size.

Every reaction card shows its own master mix table (auto-scaled to your sample count), replicate run dates, a Notes field, and a **Generate Instructions** button that produces a print-ready PDF — recipe, thermocycler program, gel-loading instructions with an agarose-gel-making recipe table, and expected product size.

## Results & gels

- **Results table**: one fast-entry grid (Actin + 3 replicates each of Hellgren/Drovetski/Ciloglu). Select cells by click/drag/shift-click, then stamp them Positive, Weak Positive, or Negative with one click — no typing, no dropdowns.
- **Band details**: a dedicated modal lets you check off which specific band(s) were present on any Positive/Weak Positive call, shown as a sub-line under the main result.
- **Gel images**: 19 upload slots (one per reaction replicate) with automatic color inversion, lane detection, and auto-labeling from your Bird ID list — crop, relabel, and annotate as needed, then download the labeled gel as a PNG.
- **CSV export**: separate downloads for the results grid and the band-detail breakdown.

## Reports

- **Print Dilution Table** — a bench-ready printout of the Step 1 table.
- **Print General PCR Advice** — a one-page reference sheet on reagent handling and master-mix assembly order.
- **Generate Final Report** — one combined PDF: the results summary grid, the dilution table, and every PCR's master mix, notes, replicate dates, and labeled gel images, laid out section by section.

## Save & load

Use **Save Comparison Data** / **Load Previous Comparison** to persist everything — samples, concentrations, dates, results, band details, notes, and all 19 gel images — to a file and pick it back up later, since the different PCRs and their gels often happen on different days.

## Project structure

```
Avian_Malaria_Methods_Comparison.html   the entire tool — HTML, CSS, and JavaScript
                                         (including the bundled jsPDF, jsPDF-AutoTable,
                                         UTIF.js, and pako libraries), all in one file
README.md                               this file
```

There is no build process. To make changes, edit the HTML file directly.
