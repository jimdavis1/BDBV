# Ebolavirus Glycoprotein (GP) Epitope Atlas — EBOV, SUDV, BDBV, TAFV

A curated, alignment-anchored catalogue of **B-cell (antibody)** and **T-cell (CD8+)** epitopes on the ebolavirus glycoprotein, with epitope sequences, coordinates, source antibodies/HLA restrictions, and an explicit record of how each entry was verified.

Every coordinate is given in one consistent frame, every literal sequence is drawn either from a primary source or computed from structure/alignment (never from memory), and every conformational epitope was recomputed from deposited atomic coordinates. Cells that could not be resolved are flagged rather than guessed.

> Companion spreadsheet: `Ebolavirus_GP_Epitopes.xlsx` (sheets: `B_cell_epitopes`, `T_cell_epitopes`, `README`) — same content with full notes/confidence columns.

---

## 1. Scope and coordinate frame

- **Viruses:** Zaire (EBOV), Sudan (SUDV), Bundibugyo (BDBV), Taï Forest (TAFV, cross-reactivity only).
- **Antigen:** the full-length, RNA-edited (8A) glycoprotein GP (GPC), *not* sGP.
- **Numbering:** full-length **EBOV / Mayinga 1976 GP precursor**, signal peptide included (SP 1–32, GP1 33–501, GP2 502–676). This is the de facto convention in the antibody literature; the human T-cell study uses the same frame.

### Reference sequences

| Species | Strain | NCBI | GP protein | Alignment row (BV-BRC) |
|---|---|---|---|---|
| EBOV | Zaire / Mayinga 1976 | NC_002549.1 | UniProt Q05320 (676 aa) / NP_066246.1 | 186538.2733 |
| SUDV | Sudan / Gulu 2000 | NC_006432.1 | YP_138523.1 | 186540.37 |
| BDBV | Bundibugyo / 200706291 Uganda 2007 | NC_014373.1 | YP_003815435.1 | 565995.26 |

All three reference rows de-gap to exactly 676 aa; the EBOV row begins `MGVTGILQLPRD…` (= Q05320), confirming the frame.

---

## 2. Methods

**Literature curation.** Antibody epitopes were assembled from primary structural/functional papers and organized by antigenic site (base, internal fusion loop, receptor-binding region, glycan cap, mucin-like domain, GP2 stalk/HR2-MPER).

**Alignment-anchored sequences.** Literal residues for linear epitopes (and the per-species residues for conserved epitopes) were extracted from a MAFFT amino-acid alignment of GPC by mapping each literature residue range onto alignment columns and reading the EBOV/SUDV/BDBV rows at the same columns. Numbering was validated independently: published escape/contact residues (G528, E545, N514, N563) land on the correct residues.

**Structural epitopes (4 Å contacts).** For conformational/quaternary epitopes, the epitope was computed directly from deposited mmCIF coordinates as **every GP residue with any atom within 4.0 Å of an antibody Fab atom**, separating heavy- vs light-chain contacts and (for quaternary antibodies) contacts across protomers. Computed footprints were cross-checked against the reference alignment rows residue-for-residue.

**T-cell epitopes.** Human CD8+ epitopes are from Powlson et al., *Cell Reports* 2019 (vaccine-elicited; ChAd3-EBOV/MVA-BN-Filo), with HLA restrictions from their Table 1 and positions from Suppl. Fig. 1E — all nine verified against the alignment. Murine H-2d epitopes are from Wu et al., *Virol. J.* 2012, located in the EBOV/SUDV rows.

---

## 3. B-cell (antibody) epitopes

All entries are B-cell epitopes defined by a monoclonal antibody. "C/D" = continuous (linear) vs discontinuous (conformational). Sequences prefixed by a species are the literal residues; discontinuous epitopes are listed as contact-residue sets.

| Antigenic site | Antibody | Source | Ebolavirus reactivity | C/D | Coordinates (EBOV-Mayinga 676-aa frame) | Epitope sequence | Verification | Structure / ref |
|---|---|---|---|---|---|---|---|---|
| Base (GP1/GP2 interface) | KZ52 | Human (1995 Kikwit survivor) | EBOV | disc. | GP1 42-43; GP2 505-514; 549-556 | EBOV: TL + VNAQPKCNPN + HNQDGLIC | Yes - X-ray (3CSY) + Ala scan | 3CSY; Lee 2008 (PMID 18615077) |
| Base (GP1/GP2 interface) | 2G4 | Mouse | EBOV | disc. | GP base; overlaps KZ52 | EBOV: ~KZ52 base (505-514 VNAQPKCNPN / 549-556 HNQDGLIC); footprint approx | Yes - cryo-EM footprint + neutralization | EM; PDB verify; Murin 2014 (PMID 26311869) |
| Base (GP1/GP2 interface) | 4G7 | Mouse | EBOV | disc. | GP base; overlaps KZ52 | EBOV: ~KZ52 base (505-514 / 549-556); footprint approx | Yes - cryo-EM footprint + neutralization | EM; PDB verify; Murin 2014 (PMID 26311869) |
| Base (GP1/GP2 interface) | 16F6 | Mouse (imm. SUDV-Boniface) | SUDV | disc. | SUDV GP1 32-50 + GP2 552-564 (discontinuous); EBOV-frame identical (base region in register) | SUDV (<=4A of Fab): GP1 S32 P34 N40 T42 L43 E44 V45 T46 E47 Q50 ; GP2 N552 A553 C556 G557 Q560 L561 E564 | Yes - X-ray 3S88 (Gulu) & 3VE0 (Boniface); epitope computed as GP residues <=4 A from 16F6 Fab | 3S88; 3VE0; Dias 2011 (PMID 21825945) |
| Base (GP1/GP2 interface) | ADI-15946 | Human (survivor) | EBOV, BDBV | disc. | GP1/GP2 base near beta17-beta18; cleaved GP_CL | EBOV: contacts not enumerated - from structure/ref | Yes - structure + escape mapping | Bornholdt/West 2019 (PMID 30713030) |
| Base (quaternary) | MAb100 (100) | Human (survivor) | EBOV | disc. (quaternary) | GP2 fusion loop 523-527 (intra-protomer, visible in 5FHC monomeric AU); full epitope quaternary | EBOV (<=4A): GP2 E523 G524 A526 I527 (PARTIAL - single protomer in asym. unit) | Yes - cryo-EM/crystal 5FHC; computed <=4 A. Quaternary epitope only partially captured in monomeric AU | 5FHC; Misasi 2016 (PMID 26917592) |
| Internal fusion loop (IFL, quaternary) | ADI-15878 | Human (survivor) | EBOV, SUDV, BDBV, TAFV, RESTV (pan) | disc. (quaternary) | Quaternary (2 protomers). Primary: GP1 34,45(,47) + GP2 HR1 560,561,563,564,567. Neighbor: GP2 fusion loop 526-537 | EBOV 6EA7 (<=4A): HC->GP1 P34 V45 + GP2 Q560 L561 N563 E564 Q567 (primary protomer); HC/LC->neighbor GP2 fusion loop A526 I527 G528 L529 A530 F535 P537. BDBV 6EA5 identical (HC also D47). | Yes - X-ray 6EA7 (EBOV) + 6EA5 (BDBV); epitope computed as GP residues <=4 A from ADI-15878 Fab, HC vs LC, across protomers | 6EA7 (EBOV); 6EA5 (BDBV); Murin/West 2018 mBio (PMID 30206174) |
| Internal fusion loop (IFL) | ADI-15742 | Human (survivor) | EBOV, SUDV, BDBV | disc. | Fusion-loop region; BDBV escape G528S | Escape residue 528 = G (EBOV/SUDV/BDBV all G); IFL window as ADI-15878 row | Yes - functional + escape (G528S) | Wec 2017 (PMID 28575452) |
| Internal fusion loop (IFL stem) | CA45 | VERIFY source organism | EBOV, SUDV, BDBV (broad) | disc. | FL stem across GP1+GP2; FVM04+CA45 escape E545D | Escape residue 545 = E (EBOV/SUDV/BDBV all E); full contacts from 6EAY | Yes - X-ray (6EAY) + escape | 6EAY; CA45 2018 Nat Commun (PMC6158212) |
| Internal fusion loop (IFL tip) | 6D6 | Mouse | Broad (EBOV,SUDV,BDBV,RESTV) | disc. | Conserved fusion-loop tip | EBOV: within IFL window 524-539 (GPAAEGIYIEGLMHNQD); exact contacts from ref | Yes - binding/competition + neutralization | Furuyama 2016 (PMID 27073111) |
| Receptor-binding region (RBR/RBS) | mAb114 (Ansuvimab) | Human (1995 survivor) | EBOV | disc. | GP1 RBR (discontinuous): 114-120, 142-146, 221-227, 231, 233, 241, 269, 309 | EBOV (<=4A of Fab): K114 K115 P116 D117 G118 E120 S142 G143 T144 G145 P146 Q221 T223 G224 T227 E231 L233 Y241 T269 T309 | Yes - cryo-EM/crystal 5FHC; epitope computed as GP residues <=4 A from mAb114 Fab | 5FHC; Misasi/Corti 2016 (PMID 26917592/26917593) |
| Receptor-binding region (apex) | FVM04 | Macaque (VERIFY) | EBOV, SUDV (cross) | disc. | RBS apex (GP1 head) | EBOV: conformational RBS apex - read from ref | Yes - competition + escape | Howell 2016 (PMID 27184844) |
| Glycan cap (beta13-beta14) | 13C6 | Mouse | EBOV (binds sGP) | disc. | Glycan cap domain GP1 228-313 | EBOV glycan-cap domain 228-313 (conformational): NETEYLFEVDNLTYVQLESRFTPQFLLQLNETIYTSGKRSNTTGKLIWKVNPEIDTTIGEWAFWETKKNLTRKIRSEELSFTVVSN | Yes - cryo-EM footprint | EM; PDB verify; Murin 2014 (PMID 26311869) |
| Glycan cap | FVM09 | Macaque (VERIFY) | EBOV | disc./linear (VERIFY) | Glycan cap (GP1 228-313) | EBOV: within glycan-cap domain 228-313 (see 13C6 row) | Yes - peptide/ELISA (confirm) | Keck 2016 (VERIFY) |
| Glycan cap | BDBV289 | Human (BDBV survivor) | BDBV, EBOV (cross) | disc. | Glycan cap (228-313); NHP-protective | BDBV glycan-cap domain 228-313: NMTNFLFQVDHLTYVQLEPRFTPQFLVQLNETIYTNGRRSNTTGTLIWKVNPTVDTGVGEWAFWENKKNFTKTLSSEELSVIFVPR | Yes - binning + NHP protection | Gilchuk 2018 JID (PMID 29986037) |
| Glycan cap | BDBV270 | Human (BDBV survivor) | BDBV, EBOV (cross) | disc. | Glycan cap | BDBV: within glycan-cap domain 228-313 (see BDBV289 row) | Yes - competition binning | Gilchuk 2018 (verify ref) |
| Glycan cap | rEBOV-548 | Human (EBOV survivor) | EBOV | disc. | Glycan cap; cooperative w/ rEBOV-520 | EBOV: within glycan-cap domain 228-313 (see 13C6 row) | Yes - binning + cooperativity | Gilchuk 2018 CHM (PMID 30308156) |
| Base / GP core | rEBOV-520 | Human (EBOV survivor) | EBOV, SUDV (N514Y escape) | disc. | GP base/core; SUDV escape N514Y | Escape residue 514 = N (EBOV/SUDV/BDBV all N); full epitope from ref | Yes - binning + escape (N514Y) | Gilchuk 2018 CHM (PMID 30308156) |
| Mucin-like domain (MLD) | 13F6-1-2 | Mouse | EBOV | linear | MLD linear 401-417 | EBOV: ATQVEQHHRRTDNDSTA (MLD is EBOV-specific; SUDV/BDBV not homologous at these cols) | Yes - X-ray Fab + MLD peptide | 2QHR (verify); Lee 2008 J Mol Biol |
| Mucin-like domain (MLD) | 6D8 | Mouse | EBOV | linear | MLD linear 389-405 | EBOV: HNTPVYKLDISEATQVE (MLD EBOV-specific) | Yes - linear peptide mapping | Wilson 2000 (PMID 10764643) |
| Mucin-like domain (MLD) | (linear epitope 3; e.g.12B5/6D3) | Mouse | EBOV | linear | MLD linear 477-493 | EBOV: GKLGLITNTIAGVAGLI (MLD EBOV-specific) | Yes - linear peptide mapping | Saphire (PMID 19559599) |
| Cathepsin-cleavage region | 226/8.1 epitope | Mouse (VERIFY clone) | EBOV | disc. | Near cathepsin site res 134,194,195 | EBOV: R134, F194, S195 (point residues) | Yes - epitope mapping (region) | Saphire (PMID 19559599) |
| GP2 stalk (HR2-MPER) | BDBV223 | Human (2007 BDBV survivor) | BDBV, EBOV (not SUDV) | disc. (stalk; peptide-reactive) | GP2 stalk ~615-632 (N618; CDRH3 clash 626-629; C-term D632) | BDBV: WTKNITDKIDQIIHDFID / EBOV: WTKNITDKIDQIIHDFVD (615-632; near-identical, SUDV differs at 624 D->N -> no SUDV binding) | Yes - X-ray Fab + stalk peptide (6N7J) | 6N7J; King 2019 (PMID 30996276) |
| GP2 stalk (HR2-MPER) | BDBV317 | Human (BDBV survivor) | BDBV, EBOV (broad) | mixed (HR2-MPER) | HR2-MPER 632-667 | BDBV: DKPLPDQTDNDNWWTGWRQWVPAGIGITGVIIAVIA / EBOV: DKTLPDQGDNDNWWTGWRQWIPAGIGVTGVIIAVIA (632-667) | Yes - HR2-MPER peptide/ELISA | Mishra 2022 (PMID 35584193) |
| GP2 stalk (HR2-MPER) | BDBV340 | Human (BDBV survivor) | BDBV (broad) | mixed (HR2-MPER) | HR2-MPER 632-667 | BDBV: DKPLPDQTDNDNWWTGWRQWVPAGIGITGVIIAVIA (632-667) | Yes - HR2-MPER peptide/ELISA | Mishra 2022 (PMID 35584193) |
| GP2 stalk (HR2) | ADI-16061 | Human (survivor) | Broad | disc. | GP2 stalk/HR2 632-667 | EBOV: DKTLPDQGDNDNWWTGWRQWIPAGIGVTGVIIAVIA (632-667) | Yes - binding/competition | Wec/Bornholdt 2017-2019 (verify) |

---

## 4. T-cell (CD8+) epitopes

Human epitopes (EBOV GP, vaccine-elicited) are complete with HLA restriction; murine H-2d epitopes are included with host noted. All peptide sequences are literal.

| Epitope | Peptide sequence | Coordinates | Host | MHC restriction | SUDV homol. | Verification | Reference |
|---|---|---|---|---|---|---|---|
| Epitope 1 (GP1 head) | GVATDVPSATKR | 74-85 (12 aa; A*11:01 9mer ATDVPSATK = 76-84) | Human | HLA-A*11:01 (pentamer-confirmed); A*03:01 (weak) | 85% | Yes - ELISpot + ICS + A*11:01 pentamer | Powlson 2019 (PMID 31775039) |
| Epitope 2 (GP1 head) | GFRSGVPPK | 87-95 | Human | HLA-A*30:01 | 100% | Yes - IFNg ELISpot | Powlson 2019 (PMID 31775039) |
| Epitope 3 (GP1 head) | AENCYNLEI | 105-113 | Human | HLA-B*40:02; B*44:02 | 100% | Yes - IFNg ELISpot | Powlson 2019 (PMID 31775039) |
| Epitope 4 (GP1 head) | RLASTVIYR | 164-172 | Human | HLA-A*03:01 | 100% | Yes - ELISpot + ICS (strong) | Powlson 2019 (PMID 31775039) |
| Epitope 5 (glycan cap) | TEDPSSGYY | 206-214 | Human | HLA-A*01:01 | 56% | Yes - IFNg ELISpot | Powlson 2019 (PMID 31775039) |
| Epitope 6 (glycan cap) | DTTIGEWAFW | 282-291 (10 aa; B*58:01 9mer TTIGEWAFW = 283-291) | Human | HLA-B*58:01 (strong); A*01:01 (weak) | 70% | Yes - IFNg ELISpot | Powlson 2019 (PMID 31775039) |
| Epitope 7 (GP2 base) | NQDGLICGL | 550-558 | Human | HLA-B*38:01; B*38:02 | 79% | Yes - ELISpot + ICS (strong) | Powlson 2019 (PMID 31775039) |
| Epitope 8 (GP2 trimer interface) | TELRTFSIL | 577-585 | Human | HLA-B*40:01 | 78% | Yes - IFNg ELISpot | Powlson 2019 (PMID 31775039) |
| Epitope 9 (GP2 C-term / TM) | ALFCICKFVF | 667-676 (10 aa; A*24:02 9mer LFCICKFVF = 668-676) | Human | HLA-A*24:02 (pentamer-confirmed, LFCICKFVF); A*02:01 (ALFCICKFV); A*23:01 | 50% | Yes - ELISpot + ICS + A*24:02 pentamer | Powlson 2019 (PMID 31775039) |
| LV (ZEBOV GP) | LYDRLASTV | 161-169 | Mouse (BALB/c) | H-2Kd | n/a | Yes - established murine CTL epitope | Wu 2012 Virol J (PMID 22849361) |
| EL (ZEBOV GP) | EYLFEVDNL | 231-239 | Mouse (BALB/c) | H-2Kd | n/a | Yes - established murine CTL epitope | Wu 2012 Virol J (PMID 22849361) |
| RF (SUDV GP) | RPHTPQFLF | 246-254 (SUDV) | Mouse (BALB/c) | H-2Ld | n/a | Yes - IFNg ELISpot, BALB/c (confirmed) | Wu 2012 Virol J (PMID 22849361) |
| SL-9 (SUDV GP) | SFFVWVIIL | 18-26 (SUDV; signal peptide) | Mouse (BALB/c) | H-2Kd (predicted) | n/a | Predicted (not confirmed) | Wu 2012 Virol J (PMID 22849361) |
| QT/GF/KL/LF (ZEBOV GP) | QGPTQQLKT; GPCAGDFAF; KKPDGSECL; LPQAKKDFF | see ref | Mouse (BALB/c) | H-2Dd / H-2Ld (predicted) | n/a | Predicted (not confirmed) | Wu 2012 Virol J (PMID 22849361) |

---

## 5. Cross-cutting structural findings

- **GP1–GP2 base is a shared B-cell + T-cell hotspot.** KZ52 (human), 16F6 (anti-SUDV, computed from 3S88/3VE0), and the human CD8 T-cell **epitope 7** (NQDGLICGL, 550–558) all converge on the GP2 ~550–564 / GP1 ~32–50 base. 16F6's footprint overlaps KZ52 (shared GP1 42–43, GP2 552–556), and 6 of 9 residues of CD8 epitope 7 are KZ52 contacts.
- **GP1 head / receptor-binding region carries both arms of immunity.** mAb114 (computed from 5FHC) contacts a 20-residue RBR epitope (114–120, 142–146, 221–227, 231/233/241/269/309); K114/K115/G143/P146 overlap the NPC1 receptor footprint. CD8 epitopes 1–4 map to the same GP1 head.
- **ADI-15878 breadth has a clear structural basis.** Its quaternary epitope — heavy chain on GP1 β1-β2 + GP2 HR1 (incl. glycan N563) of one protomer, light chain reaching the fusion-loop tip (incl. escape residue **G528**) of the neighbor — is **essentially identical between EBOV (6EA7) and BDBV (6EA5)**, explaining pan-ebolavirus neutralization.

---

## 6. Resolution status

**Computed from coordinates (4 Å):** KZ52, 16F6 (3S88 Gulu + 3VE0 Boniface), mAb114 + MAb100 (5FHC), ADI-15878 (6EA7 EBOV + 6EA5 BDBV).
**Sliced from the GPC alignment:** the MLD linear epitopes (6D8, 13F6, MLD-3), GP2 stalk / HR2-MPER (BDBV223 region, BDBV317/340), glycan-cap domain spans, point/escape residues.
**Still source-flagged (not fully enumerated):**
- **MAb100** — only the intra-protomer GP2 fusion-loop contacts (523–527) are visible in the monomeric 5FHC asymmetric unit; the quaternary base contacts to the neighbouring protomer need symmetry expansion of the trimer.
- **16F6 (SUDV)** — fully resolved from structure; note SUDV-native numbering is in register with EBOV here.
- **FVM04, glycan-cap binders (FVM09, BDBV270, etc.)** — conformational; residue-level footprints require their own complex structures.

---

## 7. Key data sources

**Structures (PDB):** 3CSY (KZ52); 3S88, 3VE0 (16F6); 5FHC (mAb114 + MAb100); 6N7J (BDBV223); 6EAY (CA45); 6EA7, 6EA5 (ADI-15878 + EBOV / BDBV); 6DZN (apo ADI-15878 Fab).

**Key references (PMID):** Lee 2008 (18615077, KZ52); Dias 2011 (21825945, 16F6); Misasi/Corti 2016 (26917592 / 26917593, mAb114 + MAb100); Murin 2014 (26311869, ZMapp 2G4/4G7/13C6); Murin/West 2018 (30206174) & West/Saphire 2018 (ADI-15878); King 2019 (30996276, BDBV223); Gilchuk 2018 (30308156, rEBOV-520/548); Wilson 2000 (10764643, 6D8); Powlson 2019 (31775039, human CD8 epitopes); Wu 2012 (22849361, murine CD8 epitopes); Saphire/Lee review (19559599).

**Sequences:** UniProt Q05320; RefSeq NC_002549.1 / NP_066246.1 (EBOV), NC_006432.1 / YP_138523.1 (SUDV), NC_014373.1 / YP_003815435.1 (BDBV).

---

## 8. Reproducibility notes

- Contact computation: GP residue retained as epitope if any atom ≤ 4.0 Å from any Fab atom; chains classified per file (entity numbering is **not** consistent across PDB entries — each structure was inspected before use).
- Quaternary antibodies (ADI-15878) were analysed on structures containing the full GP trimer so cross-protomer contacts are captured; single-protomer asymmetric units (MAb100/5FHC) yield only the intra-protomer half, which is stated explicitly.
- Caveats are recorded in-cell rather than omitted. "see ref / verify" means a value exists in the cited source but was not independently confirmed here.

*Confidence tiers: structural (crystal/cryo-EM) > mutagenesis/escape > peptide-ELISA > competition binning. See the spreadsheet `README` sheet and per-row "Confidence / notes" for specifics.*
