# BDBV
## This repo contains sequence data relating to the 2026 Ebola Bundibugyo outbreak
Publicly available genomes were sourced from BV-BRC on May 28, 2026 and re-annotated with LowVan. 
Outbreak genomes were obtained from Pathoplexus and should be considered embargoed.  Please refer to the pathoplexus website for information on redistribution.

## Repo Contents
**/Annotated_Genomes** (New BDBV genomes from pathoplexus annotated with LowVan)

**/Metadata** (Metadata from pathoplexus, and genome names from BV-BRC)

**/Alignments** (fasta-formatted amino acid alignments for glycoproteins generated with mafft)

**/NWK_Trees** (Newick-formatted tree files generated using FastTree)

**/HTML_Trees** (html trees rendered from the Newick files (see below))


## Trees
Current trees can be viewed here:

https://jimdavis1.github.io/BDBV/HTML_Trees/GPC.html

https://jimdavis1.github.io/BDBV/HTML_Trees/Gn.html

https://jimdavis1.github.io/BDBV/HTML_Trees/Gc.html

https://jimdavis1.github.io/BDBV/HTML_Trees/sGP.html

https://jimdavis1.github.io/BDBV/HTML_Trees/ssGP.html

## Covered proteins
I am currently providing alignments and trees for the following proteins

**GPC**: Pre-glycoprotein polyprotein GP complex

**Gn**: Mature N-terminal envelope glycoprotein

**Gc**: Mature C-terminal envelope glycoprotein Gc

**sGP**: Mature soluble secreted glycoprotein sGP

**ssGP**: Small soluble glycoprotein ssGPs

## General note on transcript editing
In the ebola viruses, transcript editing creates diversity in the glycoproteins.  Basically, the polymerase encounters a special low-complexity motif, pauses, and inserts an extra A into the RNA transcript.  The result (more or less) looks like this:

  aaaaaacttcacaaaaa  sGP transcript (unedited)

 aaaaaa**A**cttcacaaaaa  GN and GPC

aaaaaa**AA**cttcacaaaaa  ssGP

Where the uppercase As denote new bases that are not encoded on the template strand. If you work directly from the genome sequence you should account for this in your resulting proteins.  


## General remarks on data quality.

On May 28, 2026, there were 15 Bundibugyo sequences in pathoplexus from the current outbreak.  10 of these were "Good" quality from LowVan and 5 were poor.  The 10 good quality strains are shown in the GPC tree.  Of these, the 5-15 and 5-16 strains still had a few X characters in their sequences.  This may impact their branching patterns. 



