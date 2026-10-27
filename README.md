# MultiSoil

<p align="center">
  <img src="assets/MycologyMicrobiologyCenter_logo.png" alt="Mycology and Microbiology Center" width="300">
</p>


The study developed a multi-component Soil Health Index (SHI) for croplands and evaluated agrochemical, functional and DNA-based indicators of soil health. Soil samples were collected from 30 winter wheat fields in Estonia at two depths (0-10 cm, in two replicates, and 0-20 cm), giving 90 samples for DNA analyses.

## Contents

| File                     | Marker                                 | Target group         | Sequencing       | Features                     |
| ------------------------ | -------------------------------------- | -------------------- | ---------------- | ---------------------------- |
| `MultiSoil_16S.xlsx`     | 16S rRNA gene, V4-V5 (515F / 926R)     | Bacteria and Archaea | Illumina NovaSeq | 48,126 ASVs                  |
| `MultiSoil_ITS.xlsx`     | Full-length ITS (ITS9mun / ITS4ngsUni) | Fungi and protists   | PacBio Revio     | 23,948 OTUs (98% similarity) |
| `MultiSoil_Metazoa.xlsx` | COI (mlCOIintF / jgHCO2198)            | Metazoa              | Illumina NovaSeq | 1,147 OTUs (97% similarity)  |

Each table contains one row per ASV/OTU, read counts per sample (columns `MS*`), and taxonomic annotation. 
The 16S table also includes functional assignments (e.g., ammonification, nitrogen fixation, plant pathogens), 
and the ITS table includes fungal guild and trait annotations (primary guild, plant pathogenicity, thallus type, biocontrol potential).

Bioinformatic processing:
- 16S: Cutadapt, USEARCH, DADA2; taxonomy against GTDB; tag-jump removal with UNCROSS2  
- ITS: [NextITS](https://github.com/vmikk/NextITS) v1.2.0; taxonomy against EUKARYOME v2.0  
- COI: DADA2 workflow in [PipeCraft2](https://github.com/pipecraft2/pipecraft) v1.2.2; taxonomy with SINTAX against CO1Classifier v5.1.0; non-metazoan, chordate and putative NUMT sequences removed  

See the Methods section of the manuscript for details.

