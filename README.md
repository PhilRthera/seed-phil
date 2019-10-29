# # # #

  Title : README.md
  Contents : Documentation Guidelines + Architecture for Translational Sampling Pipeline Service

# # # #

Technical Milestones :

1/ CRISPR substrates :

    1.1/ nanobody

      1.1.1/ Objective :: Engineer complementary set of antibodies (i.e. nanobodies) for a
      given indication relevant Protein receptor/tumour associate antigen/Neoantigen substrate.

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
        
        1.1.4/ Target Definition
        RNA seq (inhouse sequencing and public databases) provide the design information for selection of membrane associate target.   
        With a forward look and where targets are poorly defined for an indication (IHC, RNAseq, etc), potential unbiased library 
        screening could be applied upon whole cell, followed by target recovery.

          1.1.3.1/ Libraries


 Libraries provide us with complementary options for discovery of VHH (nanobodies). The 3 options provide us with robust screening choices. VHH screening against different targets broadens the delivery compacity of the Nuc-Nab system.
            #1/ Jenthera library
            In house VHH library with hypervariability at CDR2 and CDR3 regions

            #2/ Superhuman library - 
            Accessed via Dac and Digitalis

            #3/ Discovery Services : 
            Hybrigenics provides us with a fee for service option using their synthetic VHH library. Lead is Jean Christophe Rain, deep
            experience in library construction and screening. Jenthera has discussed and explored options for improvements of their 
            VHH process with a view for potential collaboration outside of a fee for service at a later date.
      

            https://www.criver.com/sites/default/files/resource-files/DS-DS-services-and-facilities.pdf

      1.1.4/ Engineered Output : Complementary set of antibodies (i.e. nanobodies) for a
      given indication relevant Protein receptor/tumour associate antigen/Neoantigen substrate.

      1.1.5/ Cost Upper Bound : to be discussed with Phil
      Cost follow up in next meeting. Cost should be considered with respect to the 3 screening options. To create robust screening
      application of minimum 2 options should be explored. Hybrigenics discovery service starts at $9400 per vhh, with additional VHH 
      optimisation and characterisation services coming at additional cost.

      1.1.6/ Staging/Operations : to be discussed with Phil

    1.2/ guide RNAs

        1.2.1/ Objective :: Engineer complementary set of guide RNAs for a
        given clinically-oriented genomic locus. Locus determined by well established synthetic lethality networks in BRCA1 genetic back
        ground in Breast cancer and HLA typing. In the context of PARP resistance the use case is focused on genomic targets within 
        homologous recombination pathway (and alternative pathways), principally Rad51/52 as both are shown to recover PARP function
        as well as be SL in cancer singularly. SL combination of Rad51/52 disruption and PARP resistance is well validated in the 
        experimental and clinical context.

        1.2.2/ Solution :: Physicochemical construction as per discussion with Phil by way of the Jenthera platform.

        1.2.3/ Engineering Parameters :: As per discussion with Phil, Jenthera's platform is the
        ideal solution to construct clinically-oriented guide RNAs.

            1.2.3.1/ Libraries

              #1/ Jenthera library

        1.2.4/ Engineered Output : Complementary set of guide RNAs for a
        given clinically-oriented genomic locus. Test group of Rad 52/51 gRNAs designed.

        1.2.5/ Cost Upper Bound : to be discussed with Phil gRNA start at $109-300 each. For each locus a minimum of 4-6 gRNA of high 
        quality and specificity should be experimentally evaluated against phenotypic outcome

        1.2.6/ Staging/Operations : to be discussed with Phil

3/ PDX (Patient-Derived Xenograft) Models ; Chick Models

    3.1/ Translation Rescue Experiments

        1.1.1/ Objective :: Demonstrate ability or inability of engineered CRISPR nanobody/guide RNA pairs
        to rescue tumor growth in targeted mouse genomic backgrounds.  

        3.1.2/ Solution :: As discussed with Phil, we can take advantage of several existing PDX pipeline services. Most importantly, 
        this solution is in keeping with our internal objective of de-noising
        the general services pipeline. This will also be a general testbed for goodness of fit in working with Jackson Labs (JAX) PDX 
        services longitudinally. Our hope here is that we can establish a
        working example of a pipeline, along with all of the required handoffs as an instance of
        the internal architecture that we will presumably propagate.

        3.1.3/ Engineering Parameters :: As per discussion with Phil, the parameters of the PDX pipeline should be robust insofar as they've been industrialized (read: translated from bench science to actual working science) at JAX. With this in mind, our expectation is that the JAX repository of
        clinically-oriented mouse lines from which to generate particular genomic backgrounds suitable for
        rescue is possibly the best out there, if not the best. Forward look suggests PDX pipeline will enables us to assess clinical stage appropriate

        As discussed with Phil regarding the clinical HLA/BRCA Nature Medicine paper, presumably we
        would :
          1/ Genetically generate the required genomic backgrounds (e.g. by crossing to get, for example,
          a relevant tumorigenic haplotype like HLA-A+/+, HLA-B+/-, BRCA1+/-).
          2/ Assess engineered tumor growth in the crossed backgrounds. As per standard service practice
          3/ Assess CRISPR rescue in a PDX model using the engineered tumors.
          4/ Assess synergic treatment of PARP inhibitors with Nuc-NAB editing (based on SL targeting of Rad51/52 for 
          Parp recovery of function (rescue)

        3.1.4/ Engineered Output : Experimental set of CRISPR nanobody/guide RNA pairs that demonstrate
        rescue from explanted tumor growth of engineered genomic backgrounds. This data would also presumably
        include kinetic parameter data for the chosen clinical locus.

        3.1.5/ Cost Upper Bound : Cost of PDX study will reflect PDX choices from the database as reviewed by Phil and Dac. 
        Dac to make selection of PDX models from database.

        3.1.6/ Staging/Operations : to be discussed with Phil


4/ Sequencing Pipeline


    4.1/ Motivation : Another possibly interesting part of this problem to being considering in addition to the molecular rescue is the sequencing required to make the clinical calls for a given haplotype. In some sense, we should be checking our work here or at least doing a sense check of the given locus. In addition,
    we get the possible benefit of understanding the presence or absence of a given genomic haplotype
    in a particular fluid/tissue compartment. This, in our opinion, is where the rubber hits the road.
    One possible way to approach here is via the JAX biospecimens route. Specifically, we can and
    should construct a service pipeline that enables sequencing of clinically-oriented loci either
    of active interest to us or collaborators/other fundamental seed problems. See here for a
    description of the JAX biospecimens service:

    https://www.jax.org/jax-mice-and-services/find-and-order-jax-mice/biospecimens
