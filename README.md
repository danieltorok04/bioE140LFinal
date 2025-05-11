# bioE140LFinal
BioE 140L Final Project
1. Introduction

Lycopene is a carotenoid compound synthesized through a multi-step pathway involving the sequential actions of enzymes encoded by crtE, crtB, crtI, and idi. For this BioE 140L ortholog scan project, I selected orthologs of these four genes from phylogenetically diverse organisms to reconstruct a lycopene biosynthesis operon. The genes were amplified from genomic DNA using oligos designed for Golden Gate Assembly, creating a modular and efficient cloning strategy.

2. Gene Selection and Justification

The four genes and their respective organisms were selected based on phylogenetic diversity, enzymatic characterization, and compatibility with E. coli expression systems:

  crtE from Pseudescherichia vulneris (UniProt: P22873): Well-characterized GGPP synthase compatible with bacterial hosts. Geranylgeranyl diphosphate synthase- Catalyzes the condensation of farnesyl diphosphate (FPP) and isopentenyl diphosphate (IPP) to yield geranylgeranyl diphosphate (GGPP) needed for biosynthesis of carotenoids and diterpenes.

  crtB from Arthrospira platensis (UniProt: O07333): A cyanobacterial phytoene synthase that offers expression diversity and strong prior     characterization. Phytoene synthase- Catalyzes the reaction from prephytoene diphosphate to phytoene.

  crtI from Pantoea ananas (UniProt: P21685): Frequently used in synthetic biology, known to yield all-trans-lycopene efficiently. Phytoene desaturase (lycopene-forming) - Converts 15-cis-phytoene into all-trans-lycopene via the intermediary of all-trans-phytofluene, all-trans-zeta-carotene and all-trans-neurosporene, by the introduction of four double bonds.

  idi from Phaffia rhodozyma (UniProt: O42641): A yeast-derived isomerase, chosen to expand phylogenetic representation and optimize          precursor balancing. Isopentenyl-diphosphate delta-isomerase- Isopentenyl-diphosphate delta-isomerase; part of the second module of ergosterol biosynthesis pathway that includes the middle steps of the pathway (PubMed:9182699).
The second module is carried out in the vacuole and involves the formation of farnesyl diphosphate, which is also an important intermediate in the biosynthesis of ubiquinone, dolichol, heme and prenylated proteins (By similarity).
Activity by the mevalonate kinase first converts mevalonate into 5-phosphomevalonate (By similarity).
5-phosphomevalonate is then further converted to 5-diphosphomevalonate by the phosphomevalonate kinase (By similarity).
The diphosphomevalonate decarboxylase then produces isopentenyl diphosphate (By similarity).
The isopentenyl-diphosphate delta-isomerase then catalyzes the 1,3-allylic rearrangement of the homoallylic substrate isopentenyl (IPP) to its highly electrophilic allylic isomer, dimethylallyl diphosphate (DMAPP) (PubMed:9182699).
Finally the farnesyl diphosphate synthase catalyzes the sequential condensation of isopentenyl pyrophosphate with dimethylallyl pyrophosphate, and then with the resultant geranylpyrophosphate to the ultimate product farnesyl pyrophosphate (By similarity)

These genes provide a broad orthologous view of the pathway while remaining compatible with bacterial assembly and expression systems.

3. Oligo Design for Golden Gate Assembly

Following the JCA tutorials, oligos were designed to amplify each gene from its genomic DNA using PCR, with BsaI sites and unique 4 bp overhangs engineered into the primers to facilitate directional assembly into a single plasmid construct.

Golden Gate design rules applied:

BsaI sites: GGTCTC added in reverse orientation (5' to 3') to generate defined overhangs.

4 bp overhangs: Selected based on standard JCA part registry, avoiding palindromes and minimizing secondary structure.

Start and stop codons preserved as part of each gene.

4. Assembly Strategy

All four fragments were designed to assemble in the following order:

idi  -->  crtE  -->  crtB  -->  crtI  --> destination vector backbone

The assembly uses four PCR fragments with the following part IDs:

  frag1: idi

  frag2: crtE

  frag3: crtB

  frag4: crtI

All parts will be inserted into a common destination vector via Golden Gate Assembly using BsaI.

5. Construction File

PCR oIDI-F oIDI-R gDNA frag1
PCR oCRTE-F oCRTE-R gDNA frag2
PCR oCRTB-F oCRTB-R gDNA frag3
PCR oCRTI-F oCRTI-R gDNA frag4
GoldenGate frag1 frag2 frag3 frag4 BsaI ggFinal
Transform ggFinal Mach1 Amp 37 pLycopene

6. Oligo Table


oIDI-F: agtcGGTCTCactaATGGCTGCCGTCTTCACTGC (BsaI + acta overhang (1st position) + start codon)

oIDI-R: agtcGGTCTCgctaTCAGGCCTTGTAGTTGACGA (BsaI + gcta overhang (joins to crtE) + stop codon)

oCRTE-F: 	agtcGGTCTCgctaATGTCAGGTGTCGCATACGG (BsaI + gcta overhang (2nd position) + start codon)

oCRTE-R: agtcGGTCTCcggaTCAGTCGTAGGCGTCGAGAA (BsaI + cgga overhang (joins to crtB) + stop codon)

oCRTB-F: agtcGGTCTCcggaATGAGTTCAAGGGCGACGTG (BsaI + cgga overhang (3rd position) + start codon)

oCRTB-R: agtcGGTCTCtaccTTATTCGCGCTCCAGTCCT (BsaI + tacc overhang (joins to crtI) + stop codon)

oCRTI-F: agtcGGTCTCtaccATGGAAACAGCCTGTTGCC (BsaI + tacc overhang (4th position) + start codon)

oCRTI-R: agtcGGTCTCtgaaTTAGGCGTCCTTCGCGATG (BsaI + tgaa overhang (joins to vector) + stop codon)

7. Conclusion

This project demonstrates a full ortholog scan and assembly of a lycopene biosynthesis pathway using standard synthetic biology techniques. The selection of genes from phylogenetically diverse species allows for exploration of expression variability and optimization. The design mirrors standardized JCA workflows including BsaI-based Golden Gate Assembly and conforms to best practices for oligo construction and modular cloning.

