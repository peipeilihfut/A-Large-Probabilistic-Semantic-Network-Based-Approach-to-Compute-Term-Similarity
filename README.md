# Term-Similarity-based-on-Semantic-Network-Probase

					 
<DIV id="contentArea">
<DIV class="zone" id="mainZone">
<DIV class="compositeModule_1Zone ">
<DIV class="zone">
<DIV class="title deM"><B>A Large Probabilistic Semantic Network Based
Approach to Compute Term Similarity</B>
<DIV class="cl"></DIV></DIV>
<DIV class="conM ">
<P>&nbsp;</P>
<P>The goal of <B>our semantic similarity measurement approach</B> is to accuratly compute the semantic similarity between terms, including single words and multi-word expressions.</P>
<H2>Introduction</H2>
<P>Measuring semantic similarity between terms is a fundamental problem in lexical semantics [1] and it finds many
applications in web and document search, question and answer systems, and other text analytics and text understanding scenarios. By terms, we mean either single words or
multi-word expressions (MWEs). We say two terms are semantically similar, if their meanings are close, or the concept or object that they represent share many common attributes. For example, "emerging markets" and "developing countries" are similar because their semantic contents
(the subset of countries) are very similar. Another example,
"Google" and "Microsoft" are similar because they are both
software companies. However, "car" and "journey" are not
semantically similar but related because "car" is a transport
means for the activity "journey". Specifically, semantic similarity is defined by some measure of distance between two
terms on an isA taxonomy. It is clear that "car" and "journey" are quite far away from each other in an isA taxonomy
from WordNet as shown in Figure 1. Semantic similarity is a
more specific relationship and is much harder to model than
relatedness (which can be modeled by term co-occurrence).</P>
<P>Currently, there are two main approaches for this
task, namely the knowledge based and the corpus based
approaches. However, these approaches are more suitable
for measuring semantic similarity between two words rather
than the more general multi-word expressions (MWEs), and
scalability issues from manual tagging as well as corpora dependency
and availability also limit their applicability.</P>
<H2>Our Semantic Similarity Calculation Approach</H2>
<P>Contrary
to these existing techniques, we propose a lightweight
and effective approach (called RCP) for semantic similarity using a large
scale semantic network automatically acquired from billions
of web documents. The semantic network consists of millions
of concepts, which explicitly model the context of semantic
relationships. Given two terms, we map them into the
concept space, and compare their similarity in that space.
Furthermore, we introduce a clustering approach to orthogonalize
the concept space in order to improve the accuracy of
the similarity measure. 
<P>The main contributions of this paper are:</P>
<P>
1. Our approach has better coverage. The semantic network
behind this approach is one order of magnitude
larger than WordNet in terms of the number of hypernym-
hyponym relations. Unlike existing methods based
on WordNet which only measure the similarity between
limited number of words, our approach enables
the similarity computation between almost any two
known noun-based MWEs. This is because the knowledge
source [2] behind this approach is harnessed from
billions of web documents.</P>
<P>
2. Our approach produces more meaningful similarity. Unlike
corpus-based methods which can confuse similarity
with relatedness, this approach calculates similarity
by relations induced from an isA semantic network. It
also seeks to disambiguate terms with multiple meanings
before calculating similarity and thus excludes
noises from irrelevant senses from the probability distributions.
As a result, the similarity results are more
relevant and reliable.</P>
<P>
3. Our approach is lightweight. The most computational
intensive part of the algorithm is clustering which can
be performed online. The remaining similarity function
can be efficiently computed online. In particular,
given a pair of terms, on average, it takes merely 65
milliseconds to compute its similarity.
</P>
<P>Extensive studies demonstrate that our approach can
accurately compute the semantic similarity between terms
with MWEs and ambiguity, and significantly outperforms
12 competing methods.</P>
<H2>Three Benchmark Data Sets </H2>
<P>We use three data sets in the following experiments, 
	including two well-known benchmark data sets for word similarity and one labeled 
	data set for evaluating MWEs which is created by us. M&C data set is a subset of Rubenstein-Goodenough's [3] 
	and consists of 30 word pairs. Because of the omission of two word pairs in earlier versions of WordNet, 
	most researchers used only 28 word pairs for evaluations in the past. We follow this tradition in this 
	paper. WordSim203 is a subset from WordSim353,and has been used as a similarity testing data set by Agirre
et. al.[4] It contains 203 pairs which are considered more similar than related, where similar pairs include 
	those classiffied as synonyms, antonyms, identical, or hyponym-hypernym, and unrelated pairs indicate 
	those classiffied as none-of-the-above that had average similarity less than or equal to 0.5 (on a scale 
	of 0 to 1). Because there are no benchmark data for the semantic similarity between MWEs, we labeled 300 
	pairs (known as WP) with both words and MWEs. Our labeled data consist of three categories: 100 
	concept-entity pairs, 100 concept-concept pairs and 100 entity-entity pairs. These 300 pairs contain 
	84 word pairs and 216 MWE pairs, in which 71 MWE pairs can be identiffied by WordNet while 145 MWE 
	pairs can not be identiffid by WordNet. Five native speakers of English labeled these pairs according 
	to the label classes, and the labels are then translated into numerical similarity scores.</P>
<H2>Experiment Results</H2>
<P>Table 1 shows the experimental results on M&C data set along
with the computed similarity scores by the RCP approach. Due to the space limit, experimental results on other two data sets are not shown here, you can get details from Download.
</P>
<P align=center><B>Table 1: Semantic Similarity Scores Computed by RCP Approach on the M&C Date Set (28 Pairs)</B></P>
<P>
<TABLE class=" borderColumns borderRows tableBorder" cellSpacing=0 cellPadding=0 width=700 align=center>
<TBODY>
<TR><TD ALIGN="center" ><B>ID</B></TD><TD ALIGN="center" ><B>Term-A</B></TD><TD ALIGN="center" ><B>Term-B</B></TD><TD ALIGN="center" ><B>Human Rating</B></TD><TD ALIGN="center" ><B>Similarity Score</B></TD></TR>
<TR><TD ALIGN="center" >1</TD><TD ALIGN="center" >car</TD><TD ALIGN="center" >automobile</TD><TD ALIGN="center" >3.92</TD><TD ALIGN="center" >1.0000</TD></TR>
<TR><TD ALIGN="center" >2</TD><TD ALIGN="center" >gem</TD><TD ALIGN="center" >jewel</TD><TD ALIGN="center" >3.84</TD><TD ALIGN="center" >1.0000</TD></TR>
<TR><TD ALIGN="center" >3</TD><TD ALIGN="center" >midday</TD><TD ALIGN="center" >noon</TD><TD ALIGN="center" >3.42</TD><TD ALIGN="center" >1.0000</TD></TR>
<TR><TD ALIGN="center" >4</TD><TD ALIGN="center" >magician</TD><TD ALIGN="center" >wizard</TD><TD ALIGN="center" >3.5</TD><TD ALIGN="center" >1.0000</TD></TR>
<TR><TD ALIGN="center" >5</TD><TD ALIGN="center" >furnace</TD><TD ALIGN="center" >stove</TD><TD ALIGN="center" >3.11</TD><TD ALIGN="center" >0.9495</TD></TR>
<TR><TD ALIGN="center" >6</TD><TD ALIGN="center" >bird</TD><TD ALIGN="center" >cock</TD><TD ALIGN="center" >3.05</TD><TD ALIGN="center" >0.8235</TD></TR>
<TR><TD ALIGN="center" >7</TD><TD ALIGN="center" >boy</TD><TD ALIGN="center" >lad</TD><TD ALIGN="center" >3.76</TD><TD ALIGN="center" >0.8000</TD></TR>
<TR><TD ALIGN="center" >8</TD><TD ALIGN="center" >asylum</TD><TD ALIGN="center" >madhouse</TD><TD ALIGN="center" >3.61</TD><TD ALIGN="center" >0.8000</TD></TR>
<TR><TD ALIGN="center" >9</TD><TD ALIGN="center" >coast</TD><TD ALIGN="center" >shore</TD><TD ALIGN="center" >3.7</TD><TD ALIGN="center" >0.8000</TD></TR>
<TR><TD ALIGN="center" >10</TD><TD ALIGN="center" >journey</TD><TD ALIGN="center" >voyage</TD><TD ALIGN="center" >3.84</TD><TD ALIGN="center" >0.8000</TD></TR>
<TR><TD ALIGN="center" >11</TD><TD ALIGN="center" >food</TD><TD ALIGN="center" >fruit</TD><TD ALIGN="center" >3.08</TD><TD ALIGN="center" >0.6814</TD></TR>
<TR><TD ALIGN="center" >12</TD><TD ALIGN="center" >tool</TD><TD ALIGN="center" >implement</TD><TD ALIGN="center" >2.95</TD><TD ALIGN="center" >0.6707</TD></TR>
<TR><TD ALIGN="center" >13</TD><TD ALIGN="center" >bird</TD><TD ALIGN="center" >crane</TD><TD ALIGN="center" >2.97</TD><TD ALIGN="center" >0.5642</TD></TR>
<TR><TD ALIGN="center" >14</TD><TD ALIGN="center" >lobster</TD><TD ALIGN="center" >food</TD><TD ALIGN="center" >0.89</TD><TD ALIGN="center" >0.5247</TD></TR>
<TR><TD ALIGN="center" >15</TD><TD ALIGN="center" >brother</TD><TD ALIGN="center" >monk</TD><TD ALIGN="center" >2.82</TD><TD ALIGN="center" >0.2774</TD></TR>
<TR><TD ALIGN="center" >16</TD><TD ALIGN="center" >crane</TD><TD ALIGN="center" >implement</TD><TD ALIGN="center" >1.68</TD><TD ALIGN="center" >0.2491</TD></TR>
<TR><TD ALIGN="center" >17</TD><TD ALIGN="center" >forest</TD><TD ALIGN="center" >graveyard</TD><TD ALIGN="center" >0.84</TD><TD ALIGN="center" >0.0706</TD></TR>
<TR><TD ALIGN="center" >18</TD><TD ALIGN="center" >coast</TD><TD ALIGN="center" >hill</TD><TD ALIGN="center" >0.87</TD><TD ALIGN="center" >0.0572</TD></TR>
<TR><TD ALIGN="center" >19</TD><TD ALIGN="center" >lad</TD><TD ALIGN="center" >brother</TD><TD ALIGN="center" >1.66</TD><TD ALIGN="center" >0.0169</TD></TR>
<TR><TD ALIGN="center" >20</TD><TD ALIGN="center" >monk</TD><TD ALIGN="center" >oracle</TD><TD ALIGN="center" >1.1</TD><TD ALIGN="center" >0.0017</TD></TR>
<TR><TD ALIGN="center" >21</TD><TD ALIGN="center" >journey</TD><TD ALIGN="center" >car</TD><TD ALIGN="center" >1.16</TD><TD ALIGN="center" >0.0014</TD></TR>
<TR><TD ALIGN="center" >22</TD><TD ALIGN="center" >monk</TD><TD ALIGN="center" >slave</TD><TD ALIGN="center" >0.55</TD><TD ALIGN="center" >0.0000</TD></TR>
<TR><TD ALIGN="center" >23</TD><TD ALIGN="center" >chord</TD><TD ALIGN="center" >smile</TD><TD ALIGN="center" >0.13</TD><TD ALIGN="center" >0.0000</TD></TR>
<TR><TD ALIGN="center" >24</TD><TD ALIGN="center" >coast</TD><TD ALIGN="center" >forest</TD><TD ALIGN="center" >0.42</TD><TD ALIGN="center" >0.0000</TD></TR>
<TR><TD ALIGN="center" >25</TD><TD ALIGN="center" >glass</TD><TD ALIGN="center" >magician</TD><TD ALIGN="center" >0.11</TD><TD ALIGN="center" >0.0000</TD></TR>
<TR><TD ALIGN="center" >26</TD><TD ALIGN="center" >noon</TD><TD ALIGN="center" >string</TD><TD ALIGN="center" >0.08</TD><TD ALIGN="center" >0.0000</TD></TR>
<TR><TD ALIGN="center" >27</TD><TD ALIGN="center" >rooster</TD><TD ALIGN="center" >voyage</TD><TD ALIGN="center" >0.08</TD><TD ALIGN="center" >0.0000</TD></TR>
<TR><TD ALIGN="center" >28</TD><TD ALIGN="center" >lad</TD><TD ALIGN="center" >wizard</TD><TD ALIGN="center" >0.42</TD><TD ALIGN="center" >0.0000</TD></TR>
</TBODY></TABLE></P>
	 <div style="clear:both;"></div>
        <div class="conM "><H2>Complete Set of Results: Download</H2>
<P>More Details Refer to <A href="http://adapt.seiee.sjtu.edu.cn/similarity/SimCompleteResults.pdf" target=_new onClick="stc(this, 26)"> Complete Results on Three Data Sets</A>.</P></div>
        <div style="clear:both;"></div>
<div class="conM "><H2>References</H2>
<P>[1] A. Budanitsky and G. Hirst. Evaluating wordnet-based measures of lexical semantic relatedness. Computational Linguistics, 32:13-47,2006.</P>
<P>[2] W. Wu, H. Li, H. Wang, and K. Q. Zhu. Probase: a probabilistic taxonomy for text understanding. In Proceedings of SIGMOD'12, pages 481-492, 2012.</P>
<P>[3] H. Rubenstein and J. B. Goodenough. Contextual correlates of synonymy. Communications of the ACM, 8(10):627-633, 1965.</P>
<P>[4] E. Agirre, A. Soroa, E. Alfonseca, K. Hall, J. Kravalova, and M. Pasca. A study on similarity and relatedness using distributional and wordnet-based approaches. In Proceedings of NAACL’09, pages19–27, 2009.</P>
</div>
        <div class="conM "><H2>Contact</H2>
<P>Peipei Li(peipeili@hfut.edu.cn): Hefei University of Technology<BR><A style="ZOOM: 1" title="" href="/en-us/people/haixunw/" target=_new alt onClick="stc(this, 30)">Haixun Wang</A> (haixunw@gmail.com): Microsoft Research Asia<BR><A style="ZOOM: 1" title="" href="http://www.cs.sjtu.edu.cn/~kzhu/" target=_new alt onClick="stc(this, 29)">Kenny Q. Zhu</A> (kzhu@cs.sjtu.edu.cn): Shanghai Jiao Tong University<BR><A href="/en-us/people/zhowang/" target=_new onClick="stc(this, 28)">Zhongyuan Wang</A> (zhy.wang@microsoft.com): Microsoft Research Asia<BR><A style="ZOOM: 1" title="" href="http://www.cs.uvm.edu/~xwu/home.html" target=_new alt onClick="stc(this, 30)">Xindong Wu</A> (xwu@louisiana.edu ): University of Louisiana at Lafayette</P>
<H2>Please refer to the references for more details.</H2>
<P>Peipei Li, Hunxun Wang, Kenny Q. Zhu, Zhongyuan Wang, and Xindong Wu. Computing Term Similarity by Large Probabilistic isA Knowledge. In: Proceedings of 22nd ACM International Conference on Information and Knowledge Management (CIKM’13), pp. 1401-1410, 2013.</P>
<P>Peipei Li*, HaixunWang, Kenny Q. Zhu,Zhongyuan Wang, Xuegang Hu, and Xindong Wu. A Large Probabilistic Semantic Network based Approach to Compute Term Similarity. IEEE Transactions on Knowledge and Data Engineering, 27(10): 2604-2617, 2015.</P>
</BODY></HTML>
