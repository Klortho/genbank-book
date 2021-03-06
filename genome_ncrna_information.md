
## ncRNA Information for Annotation in GenBank

This is a guide for how to annotate Rfam output and ncRNA features for GenBank submission. The basic annotation is described in the [prokaryotic](http://www.ncbi.nlm.nih.gov/genbank/genomesubmit_annotation#RNA) and [eukaryotic](http://www.ncbi.nlm.nih.gov/genbank/eukaryotic_genome_submission_annotation#rRNA) annotation instructions.  This list of ncRNAs and Rfam products is not exhaustive and may not be the most currently correct functional assessment of these, as functions become defined for some of these RNAs. Therefore, the purpose of this page is to provide guidance on how to annotate a particular RNA. The basic logic is:

*   Annotate ribosomal RNAs as rRNA features, and tRNAs as tRNA features.
*   Annotate RNAs that belong to one of the INSDC ncRNA_classes, [http://www.insdc.org/rna_vocab.html](http://www.insdc.org/rna_vocab.html), as an ncRNA with the appropriate value in the required /ncRNA_class qualifier.
*   Some Rfam records are regions of RNAs, so they should not be annotated as RNA features. Instead:
    *   Annotate ones that bind known molecules as misc_binding features with the bound molecule in the required /bound_moiety qualifier (eg glycine riboswitch with glycine as the /bound_moiety)
    *   Annotate other regions, like leader sequences, as misc_features.

The Rfam homepage is here: [http://rfam.sanger.ac.uk/](http://rfam.sanger.ac.uk/)

Here are some examples:

*Common ncRNAs on bacteria

<pre class="real">gene            ncRNA_class      product
ffs             SRP_RNA          RNA component of signal recognition particle
rnpB            RNase_P_RNA      RNaseP RNA

*Annotate these as nc_RNA with ncRNA_class='other'

 	SraD RNA	RF00078
 	DsrA RNA	RF00014
 	SraC/RyeA	RF00101
 	RyeB		RF00111
 	SroD		RF00370
 	CsrB/RsmB	RF00018
        CsrC            RF00084
 	CO343		RF00120
 	MicC		RF00121
 	RydC		RF00505
 	SraE/RygA/RygB	RF00079  (OmrA-B RNA gene family)
 	6S/SsrS		RF00013
 	RydB		RF00118
 	RprA		RF00034
 	QUAD		RF00113
 	SraJ		RF00083
 	SraB		RF00077
 	SraG		RF00082
 	SraH		RF00081
 	CsrC		RF00084
 	RybB		RF00110
 	SroC		RF00369
 	t44		RF00127
 	sroB		RF00368
 	tke1		RF00128
 	ryfA		RF00126
 	SroE		RF00371
	ryeE		RF00112
 	suhB		RF00519
 	sroB		RF00368
 	GcvB		RF00022
 	SraD		RF00078
 	RyhB		RF00057
 	Spot 42		RF00021 (proposed antisense)
 	RtT RNA	(RttR)	RF00391 (cis-regulating RNA element that is released)
        IS183           RF00122 (new name GadY)
        IS061           RF00115
        IS102           RF00124
        CO719           RF00117
        C0299           RF00119
        CO465           RF00116
        Qrr RNA         RF00378
        PrrF RNA        RF00444
        6C RNA          RF01066
        HgcC            RF00062

*Annotate microRNA as ncRNA with ncRNA_class="miRNA"
        mir-569         RF01018

*Annotate these as antisense ncRNA with a ncRNA_class="antisense"

 	MicF		RF00033 
 	OxyS		RF00035 
 	ctRNA_p42d	RF00489
        ctRNA_pT181     RF00242
 	RNAI (RNA1)	RF00106 
 	CopA-like RNA	RF00042
 	RNA-OUT		RF00240 (antisense to the RNA-IN non-coding RNA) 
        DicF            RF00039
        sar RNA         RF00262
        Qa RNA          RF00388
 	SgrS		RF00534
        RNAIII          RF00503
        plasmid RNAIII  RF00235
        FinP            RF00107

*Catalytic introns should be annotated as ncRNAs with ncRNA_class="autocatalytically_spliced_intron"
    Group I intron (RF00028) http://rfam.sanger.ac.uk/family?acc=RF00028
    Group II intron (RF00029) http://rfam.sanger.ac.uk/family?acc=RF00029

These should be annotated as ncRNA if they occur as introns in a gene or if they occur in 
isolation. You would not need an intron feature if they interrupt a CDS. The CDS will have 
the join and then there will also be an ncRNA feature.

*Bacteria don't have a nucleolus, but they have a class of small RNAs that are similar to snoRNAs.  
Annotate these as ncRNA_class="snoRNA". eg:

     gene            42650..42727
                     /locus_tag="HMPREF9131_0857"
     ncRNA           42650..42727
                     /locus_tag="HMPREF9131_0857"
                     /ncRNA_class="snoRNA"
                     /product="putative Small nucleolar RNA SNORD19"
                     /inference="nucleotide motif:RFAM:RF00569"

* Annotate these as ncRNA with ncRNA_class="ribozyme"

 	ribozyme	product pR1 ribozyme (EU267931)
        ribozyme        product glmS riboswitch (CP000922) Rfam RF00234 (this is defined as a ribozyme)

*Riboswitches should be annotated as misc_binding feature when there is a known bound moiety and they 
aren't defined as ribozymes. A few examples are:

 	FMN riboswitch (RFN element)      bound_moiety = flavin mononucleotide
 	TPP riboswitch (THI element)      bound_moiety = thiamine/thiamin pyrophosphate
 	Cobalamin riboswitch              bound_moiety = adenosylcobalamin
 	gcvT element                      bound_moiety = glycine
 	glycine riboswitch                bound_moiety = glycine
        purine riboswitch                 bound_moiety = guanine and/or adenine
        SAM riboswitch                    bound_moiety = S-adenosyl methionine
        preQ1 riboswitch                  bound_moiety = pre-queuosine1
        lysine riboswitch                 bound_moiety = lysine

*Riboswitches with unknown functions or bound moieties are annotated as misc_features with the name in 
a note. A few examples are:

 	yybP-ykoY element or yybP-ykoY leader
 	ydaO/yuaA element 
 	ykoK element
 	ykkC-yxkD element

*Annotate these as misc_feature because they are regions of a transcript

 	S-element	        
 	rncO		                RF00552 
 	serC		                RF00517 
 	ribosomal S15 leader
 	speF		                RF00518
        Insertion sequence IS1222 ribosomal frameshifting element     RF00383
        alpha operon binding site	RF00140
        dnaX ribosomal frameshifting element                          RF00382

*T box leader can be annotated as a misc_binding feature with bound_moiety="uncharged tRNA"

*PyrR binding sites should be misc_binding feature with bound_moiety="PyrR"

*traJ 5' UTR RF00243 annotate as misc_binding with bound_moiety="FinP"

</pre>



