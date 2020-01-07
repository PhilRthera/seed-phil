# # # #

  Title : README.md
  Contents : Documentation Guidelines + Architecture for Translational Sampling Pipeline Service

# # # #

Technical Milestones :

1/ CRISPR substrates :

    1.1/ nanobody

      1.1.1/ Objective :: Engineer complementary set of antibodies (i.e. nanobodies) for a
      given Protein membrane associated target.

      1.1.2/ Solution :: Physicochemical construction as per discussion with Phil by way of the Jenthera platform.

      1.1.3/ Engineering Parameters :: As per discussion with Phil, what we need here is a
      SATURATED representation of the relevant epitope space. We can tilt the probability of
      achieving this representation by trying to get the best representation of the relevant proteome
      that we can. For example, this includes exclusion of immunogenic nanobodies that are cross-reactive
      with self and hence unsuitable. To determine the "goodness of fit" for a given representation
      we consider the kinetic parameters (i.e. phsicochemical parameters) of the system. As discussed
      with Phil, this reduces to understanding the noise characteristics of the k_d, k_a, etc parameters.
      Even a first-order Michaelis-Mentin distribution/curve should point us to the physical condition (i.e.
      library) from which to start. What we are actually try to do is iteratively, deterministically
      enrich this "starter" library. As discussed with Phil, we should be mindful that we match choice
      of library or libraries to the known state of translational targets. For example, if we start off
      with a well-known clinical target like Ras or TP53 or BRCA1 etc, we should have no short supply of
      choices from both Phil's library as well as the Superhuman library. We can then use those complementary molecules as the "starter" library. In the event that the kinetic parameters of these complementary
      moluecles is known and, after discussion with Phil and some calculations, we observe that the predicted behavior matches our intended experimental goal, we can just proceed with generation from the existing library.
        In the converse coase that we need to widen our search, we can and should sample from additional libraries. What follows is a running list of libraries of note relevant to this search space ::

          1.1.3.1/ Libraries

            #1/ Jenthera library - Currently we operate 3 different protein scaffold libraries (linear peptide 7mers, Triple Helix and 
            VHH). The latter two libraries are of our own internal design and were sequence validated 12-19th December. The basic screen 
            approach is phage display with either solid phase or bead based protein display for each round of protein target screening. 

            #2/ Superhuman library - (Kruse library - access through digitalis, clarification of commercial use required)
            https://www.kerafast.com/product/3634/yeast-display-nanobody-library-nblib cost quotes is for academic use. 
            Phil has contacted Harvard (Grant Zimmermann) directly for clarification

            #3/ Discovery Services : to be discussed with Phil - Hybrigenics discovery service (Cost upon completion $9800

            https://www.criver.com/sites/default/files/resource-files/DS-DS-services-and-facilities.pdf

      1.1.4/ Engineered Output : Complementary set of antibodies (i.e. nanobodies) for a
      given Receptor/TAA/Neoantigenic target.

      1.1.5/ Cost Upper Bound : 
            Cost upper bounds are calculated by on the choice of inhouse or external VHH production. Both are 
             provided. In each case average cost of VHH screening, assuming minimum 5 protein membrane associate antigenic targets for                VHH screening and labour for a 3mth period. This upper bound is determined by either the use of the Jenthera library or 
             Kruse. 
      
      1.1.5.1 Cost upper Bound: Commercial
                  For commerical screening assuming $9800 * 5 antigenic targets = $49000
                  Additional cost is the antigenic protein purchase or inhouse expression which is dependent upon commercial 
                  availability or internal vector generation & expression.
                  
          
      1.1.5.2 Cost upper Bound: In House Screening (Kruse or Jenthera) Total = $20000 (plus protein production $2000 per Nuc-Nab)
                 Screening Consumables (mol.bio kits, biochemicals, recombinant proteins, plastic ware): $5000
                 Labour: 3mths salary at the rate $4000 per month: $12000
                 Sequencing & Characterisation: $3000
                 Pilot production through Prof Nagar is considered a separate cost of $2000 per Nuc-Nab sent for pilot production. 
                 

      1.1.6/ Staging/Operations : to be discussed with Phil 
              1.1.6.1 - Library set up - We are setting up the Jenthera screening in the dedicated Phage facility at Illumina
                Libraries QA and screening starts 1st week of Jan
              1.1.6.2 - Selection of the 5 membrane associate targets based on the HLA/BRCA1 status - cross reference to RNA seq.
                Dac to make selection of highest relevance, which will start the selection of screening approach. The other key variable 
                is determining the selection of cells to use in testing. A clear positive control cell line should be shown expressing 
                the target of interest and ideally the biology of interest relating the PARP resistance (BRCA background) if possible. \
                Negative control cells should not have BRCA background nor receptor type targeted.
              1.1.6.3 - Performance of Screen with selectivity and biophysic characterisation. 
                          a) Sequencing: Determination of VHH sequences using iSeq/Nextera library sets
                          b) Characterisation: ELISA
                                               PhAb internalisation (Target cells versus non targetted cells)
                                               FlowCT cell assay
                                               SPR Kd analysis (if applicable)
              1.1.6.4 - Pilot production as part of Nuclease-Nab system:
                          a) Clone into Nuc-Nab base expression vectors (double digest compatible classical cloning)
                          b) Cell-free expression for rapid validation of Vector performance
                          c) Ship to Prof Nagar for Pilot production for cellular gRNA:phenotype assays (Cost of production: 2000 
                          dollars per Nuc-Nab (5x10mg/ml) plus QA)
                          d) QA Validation of internalisation & selectivity

    1.2/ guide RNAs

        1.2.1/ Objective :: Engineer complementary set of guide RNAs for a
        given clinically-oriented genomic locus.

        1.2.2/ Solution :: Physicochemical construction as per discussion with Phil by way of the Jenthera platform.

        1.2.3/ Engineering Parameters :: As per discussion with Phil, Jenthera's platform is the
        ideal solution to construct clinically-oriented guide RNAs.

            1.2.3.1/ Gene Targets

              Discussions have identified a limited subset of targets relevant to PARP resistance and recovery. 
              Currently the minimal target list is :
                
                Rad52 - Sullivan-Reed et al., 2018, Cell Reports 23, 3127–3136June 12, 2018 ª 2018 The
                        Author(s).https://doi.org/10.1016/j.celrep.2018.05.034
                Myc - Synthetic Lethality of PARP Inhibitors in Combination with MYC Blockade Is Independent of BRCA Status in Triple-
                      Negative Breast CancerJason. P.W. Carey,
                Rad51 - Rad51 - as Discussed, inclusive of Rad paraloguesUpregulation appears key to all methods of ParpI resistance 
                observed in PDX 
                        https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5961353/figure/mdy099-F1/
                        
                ATR - Inhibitions disrupts re-wired HDR alternative pathways, stabilisation of replication fork Genes Dev. 2017 Feb 
                1;31(3):318-332. doi: 
                      10.1101/gad.290957.116. Epub 2017 Feb 27
                      
                PDL1- for Dac's Evaluation - Discussed last conversation.
                
                mi622 - cell line evidence as being up regulated in BRCA mutant background leading to PARP inhibition. Leading to 
                platinium and parp resistance 
                NC_000013.11:90231167-90231290 Homo sapiens chromosome 13, GRCh38.p13 Primary Assembly
                GGCTGGGAAGAACCGAGAGAAGCTGGACAAGTACTGGTCTCAGCAGATTGAGGAGAGCACCACAGTGGT
                ATCACACAGTCTGCTGAGGTTGGAGCTGCTGAGATGACACTCACGGAGCTGAGA
                https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4731274/ Observed in Patient cohorts as well as cell lines. 
                MIR have influence upon HR component regulation other MIR have been cited as influencing PARP resistance miR-644, miR-
                492, miR-613, miR-577, miR-622 and miR-126* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4031983/?report=reader
                In the landscape of alternative target MIR provide additional viable target as they relate to the same protein targets 
                posited above. 
                
                
                NHEJ targets have been suggested for alternative PARPi escape mechanisms but to my knowledge none are observed in 
                clinical reports. E
                
                Targets chosen based on the evaluation that Rad52/51 ablation combined with ParpI leads to dual synthetic lethality. 
                In the context of Parp resistance, Rad52/51 ablation undermines the HDR mechanism. The other high potential targets are 
                rad51 a related member of the HDR mechanary to Rad52/51 and the MYC promoter which regulates components of HDR pathway 
                and Rad family members as part of DNA repair in BRCA1/2 & TNBC. 
                MYC blockades demonstrate SL with parpI irrespective of BRCA status.  
                Rad51 upregulation occurs and foci detected in all cases of ParpI escape and ATR influences Rad51 leading hence disrupts 
                alt HDR.
                Point for discussion with DAC - BRCA1/2 hypermorphs and upregulation - semi functional BRCA muts upregulated enables 
                recover of HDR function
               

        1.2.4/ Engineered Output : Complementary set of guide RNAs for a
        given clinically-oriented genomic locus.
        
                gRNA designs completed for Rad 51, MYC, Rad52 and ATR. Top 5 guides selected for cell in-vitro testing. 
                Prioritisation given to high activity and High specificity (low off target scores for loci)

        1.2.5/ Cost Upper Bound : Total = $31'000
                4 loci with 5 gRNA: $250 per gRNA: 20*250 = $5000
                Cell lines: 3 cell lines (2 cell lines BRCA1/2(-/-) and 1 cell line BRCA1/2 WT control): 3 *2000 = $6000
                Cell culture & Assay Consumables (reagents and plasticware) for 3mths: $4000
                High Level gRNA on/off target sequencing evaluation on high activity guides: $4000 
                Labour: $12'000 (3mths time period)

        1.2.6/ Staging/Operations : 
          1.2.6.1 - Final agreement on targets and gRNA between digitalis and Jenthera & budgeting
          1.2.6.2 - Ordering of cell lines & gRNA in preparation for cell line invaludation of gRNA function. Protein production occurs 
          in parallel to consumable ordering.
          1.2.6.3 - Application of Jenthera screen for gRNA editing frequency, VHH receptor mediated uptake & phenotypic modulation. 
                    Combination of the 3 metrics will be applied to determine best gRNA for each locus. Min 2 must be determined for PDX 
                    In-Vivo study. Off target is evaluated as part of gene edit frequency evaluation. 
          1.2.6.3 -  Final selection of gRNA and target, proceed to In-vivo PDX testing

3/ PDX (Patient-Derived Xenograft) Models ; Chick Models

    3.1/ Translation Rescue Experiments

        1.1.1/ Objective :: Demonstrate ability or inability of engineered CRISPR nanobody/guide RNA pairs
        to rescue tumor growth in targeted mouse genomic backgrounds.  

        3.1.2/ Solution :: As discussed with Phil, we can take advantage of several existing PDX pipeline services. Most importantly, this solution is in keeping with our internal objective of de-noising
        the general services pipeline. This will also be a general testbed for goodness of fit in working with Jackson Labs (JAX) PDX services longitudinally. Our hope here is that we can establish a
        working example of a pipeline, along with all of the required handoffs as an instance of
        the internal architecture that we will presumably propagate.

        3.1.3/ Engineering Parameters :: As per discussion with Phil, the parameters of the PDX pipeline should be robust insofar as they've been industrialized (read: translated from bench science to actual working science) at JAX. With this in mind, our expectation is that the JAX repository of
        clinically-oriented mouse lines from which to generate particular genomic backgrounds suitable for
        rescue is possibly the best out there, if not the best.

        As discussed with Phil regarding the clinical HLA/BRCA Nature Medicine paper, presumably we
        would :
          1/ Genetically generate the required genomic backgrounds (e.g. by crossing to get, for example,
          a relevant tumorigenic haplotype like HLA-A+/+, HLA-B+/-, BRCA1+/-).
          2/ Assess engineered tumor growth in the crossed backgrounds. As per standard service practice.
          3/ Assess CRISPR rescue in a PDX model using the engineered tumors.

        3.1.4/ Engineered Output : Experimental set of CRISPR nanobody/guide RNA pairs that demonstrate
        rescue from explanted tumor growth of engineered genomic backgrounds. This data would also presumably
        include kinetic parameter data for the chosen clinical locus.

        3.1.5/ Cost Upper Bound : To be determined by Phil and Dac based target selection from Cell gRNA evaluation. Currently at least 2 guides per loci is logical and selection of appropriate synergic ParpI & chemo co-dosage should be informed from Dac's clinical angle. My Personal logic is to follow agents inhibiting PARpI and DNA damage agents (PLatinum drugs and alkating agents) that have been demonstrated as synergic with DNA repair from multiple screening sources and clinical evidence. A small panel should be selected based on currently approved medications.

        3.1.6/ Staging/Operations : 
        3.1.6.1 - Select PDX models and cost evaluations based on treatment arms, number of PDXs, co-drug:gene edit synergies
        3.1.6.2 - RNAseq data sharing and Final sanity check
        3.1.6.3 - gRNA:Nuc-Nab combinations from cell study


4/ Sequencing Pipeline


    4.1/ Motivation : Another possibly interesting part of this problem to being considering in addition to the molecular rescue is the sequencing required to make the clinical calls for a given haplotype. In some sense, we should be checking our work here or at least doing a sense check of the given locus. In addition,
    we get the possible benefit of understanding the presence or absence of a given genomic haplotype
    in a particular fluid/tissue compartment. This, in our opinion, is where the rubber hits the road.
    One possible way to approach here is via the JAX biospecimens route. Specifically, we can and
    should construct a service pipeline that enables sequencing of clinically-oriented loci either
    of active interest to us or collaborators/other fundamental seed problems. See here for a
    description of the JAX biospecimens service:

    https://www.jax.org/jax-mice-and-services/find-and-order-jax-mice/biospecimens
