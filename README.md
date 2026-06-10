# Abstract

# Abstract

**A semi-supervised pipeline for a comprehensive and scalable analysis of immune heterogeneity in human samples**

David Rach1,2, Nginache Nampota-Nkomba3,4, Godfrey Mvula3, Felix A. Mkandawire3, Osward M. Nyirenda3, Winter A. Okoth5,6, Daniela Franco4, Andrea G. Buchwald5, Franklin R. Toapanta5, Marcelo B. Sztein5, Miriam K. Laufer5, Kirsten E. Lyke5, Cristiana Cairo7.

*1 Molecular Microbiology and Immunology Graduate Program, University of Maryland School of Medicine, Baltimore, MD, United States 2 Flow Cytometry Shared Resource, University of Maryland Greenebaum Comprehensive Cancer Center, Baltimore, MD, United States 3 Blantyre Malaria Project, Kamuzu University of Health Sciences, Blantyre, Malawi 4 Graduate Program in Life Sciences, University of Maryland School of Medicine, Baltimore, MD, United States 5 Center for Vaccine Development and Global Health, University of Maryland School of Medicine, Baltimore, MD, United States 6 Geographic Medicine Division, Department of Medicine, University of Maryland School of Medicine, Baltimore, MD, United States 7 Department of Microbiology and Immunology, University of Maryland School of Medicine, Baltimore, MD, United States*

Spectral flow cytometry (SFC) holds enormous potential for immune profiling in both breadth and depth. For studies of early life human immunology, where the quantity of biospecimen is limited, SFC may allow for a more thorough interrogation of immune responses following immunization or infection.

The increased number of fluorophores does come with increased uncertainty, affecting the estimation of marker abundance during unmixing. Factors such as additional or varied autofluorescence, non-specific binding or tandem degradation of fluorophores, and increased unmixing-dependent spread due to co-expression of markers on rare subsets, introduce uncertainty when analyzing datasets. Developing systematic bioinformatic methods to distinguish heterogeneity from underlying technical artifacts is critical to the production of interpretable, accurate data using SFC.

Additionally, analysis of complex SFC datasets remains a challenge. Manual gating of pre-determined cell populations of interest risks introducing bias by defaulting to past immunologic assumptions and by design narrows our ability to detect changes in other cell subsets. On the other hand, while existing unsupervised methods may capture a broader picture, it may be difficult to discern findings with biologic relevance.

Studying a cohort of Malawian infants with well-characterized prenatal HIV-exposure, we demonstrate a systematic method of analysis suitable for rare subsets. The cohort consisted of three groups of infants born to women with: A) ART-treated HIV infection and

undetectable viral load since before conception and through pregnancy (HEU-lo); B) HIV infection diagnosed and treated at mid-gestation or later, with high viral load at enrollment (HEU-hi); C) no HIV infection (HU). Cryopreserved cord blood mononuclear cells and longitudinal peripheral blood mononuclear cells collected at 4 and 9-months following routine childhood immunizations were thawed, rested for 6 hours, and stimulated in the presence of purified protein derivative (PPD) or Staphylococcal enterotoxin B (SEB). Cells were stained with a 32-color SFC panel to characterize phenotype, activation-induced markers and cytokine production with same day acquisition using a 5-laser Cytek Aurora.

Following acquisition, we carried out a semi-supervised analysis with a custom pipeline that we implemented in R and Rust. Briefly, we performed quality assurance of unmixing controls using the Luciernaga and PeacoQC R packages, replacing problematic single-colors and/or autofluorescence controls as appropriate before unmixing. Samples were biexponentially transformed and automated gating was implemented using the openCyto and flowMagic R packages. Using the interactive Shiny App in our R package Coereba, the calculated split-points between positive and negative events were visualized for each marker and manually adjusted as needed. Identity columns for the marker expression of individual cells were then generated and appended to the .fcs files.

For select cell populations, all events were concatenated, normalized with CytoNorm v2, clustered with flowSOM, and visualized with PaCMAP. Identity data associated with cells across clusters was retrieved, allowing a comparison between algorithm and manual gating performance. In parallel, cells sorted into clusters on the basis of shared marker identity were analyzed to compare their abundance between exposure groups using existing Bioconductor workflows. This mixed approach allowed us to examine the immune response across timepoints, treatment conditions and exposure groups, enabling an exhaustive, comprehensive and scalable characterization of individual heterogeneity

# Slides

This is the repository for our Cyto 2026 "Semi-supervised pipeline" parallel talk.  

Click [here](https://davidrach.github.io/AlphaBeta_Cyto2026/Rach_SemiSupervised_Cyto2026.pdf) to navigate to the .pdf of the poster, which can be downloaded. 

For our Cytometry in R course, click [here](https://umgcccfcsr.github.io/CytometryInR/course/). 

For the InstrumentQC dashboard how-to website, click [here](https://davidrach.github.io/InstrumentQC_Install/)

Click [here](https://github.com/DavidRach/Luciernaga) for information about the Luciernaga R package. 

For information about our Coereba R package, click [here](https://github.com/DavidRach/Coereba)


# GitHub Repository organization. 

Within this GitHub repository due to size limits, we are unable to provide the .svg files that were used to create the poster in [Inkscape](https://inkscape.org/), feel free to reach out to the UMGCCC Flow Cytometry Shared Resource email ("flowcore", "@", "som.umaryland.edu") to get a sharable copy. 

The code to generate QR codes and extract survey comments in R can be found under the code_poster folder. Actual QR codes generated can be found under outputs folder. Images used that were brought in from other sources can be found in the images folder. 

# License

In our commitment to open-science and open-source, all teaching materials are freely offered under a [CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/deed.en) license, while all code examples are offered under the [AGPL3-0](https://www.gnu.org/licenses/agpl-3.0.en.html) copyleft license. 