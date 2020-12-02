# AWESOME Bibliography: Survey Generation and Multi-Document Summarization

Papers and Resources for Survey Generation and Multi-Document Summarization in NLP

by Sally Ma


## Datasets
-	[Multi-News (2019)](https://github.com/tensorflow/datasets/blob/master/tensorflow_datasets/summarization/multi_news.py)
-	[WikiSum (2019)](https://github.com/nlpyang/hiersumm)
-	[DUC (2004)](https://duc.nist.gov/pubs/2004slides/duc2004.intro.pdf)
-	[TAC (2011)](https://tac.nist.gov//2011/Summarization/)


## Extractive Approach


**Maximum Marginal Relevance (MMR)** [[paper](http://www.cs.cmu.edu/~jgc/publication/The_Use_MMR_Diversity_Based_LTMIR_1998.pdf)]

Carbonell and Goldstein (1998) uses a ranking score (MMR) to produce a ranked list of the candidate sentences based on the relevance to the query and redundancy to the selected sentences, which can be used to extract sentences. 


**Lexrank** [[paper](https://www.aaai.org/Papers/JAIR/Vol22/JAIR-2214.pdf)]

Erkan and Radev (2004) turns sentences into vector representations (word embeddings) and calculates similarity matrix of the vectors and convert into graph (sentences as nodes and similarity scores as edges).


**Textrank** [[paper](https://web.eecs.umich.edu/~mihalcea/papers/mihalcea.emnlp04.pdf)]

Mihalcea and Tarau (2004) is another graph-based extractive summarization system, similar to Lexrank, that ranks sentences based on centrality (each edge being a vote), and selects the top-ranked sentences as summaries


**C-Lexrank** [[paper](http://www-personal.umich.edu/~vahed/papers/citsum.pdf)]

Qazvinian and Radev (2008) was a state-of-the-art system that uses a content model based on lexical network (fully connected network of an article, where a node is each sentence in the citation summary of the article, and a weight of an edge is the cosine similarity of pairs of sentences). The system applies lexrank in each cluster of nodes to find the most central sentences to find the most central ones for building the summary.

**HITSUM** [[paper](https://www.aclweb.org/anthology/P15-1043.pdf)]

Jha et al. (2015) proposes a new formulation of the lexical network to include additional lexical information. The system assigns hub scores (for summarizing important contributions) and authority scores (for reporting important contributions) to each node in a mutually reinforcing way and selects sentences with the highetest hub scores.


**Surveyor** [[paper](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.947.5532&rep=rep1&type=pdf)]

Jha et al. (2015) focuses on generating coherent surveys--those with well-defined and ordered subtopics. It combines a content model (modeling subtopics in a scientific paper with Hidden Markov Model) and a discourse model (modeling discourse-level dependencies for locally coherent summaries). It also introduces the idea of Minimum Independent Discourse Contexts (MIDC) of a sentence s(i): the minimum set of sentences preceding it such that s(i) can be interpreted independently of the other sentences in its text segment, in order to produce survey articles substantially more coherent and readable compared with previous work.


## Abstractive Approach

**SUMMONS** [[paper](http://www.cs.columbia.edu/nlp/papers/1995/mckeown_radev_95.pdf)] [[followup paper](https://www.aclweb.org/anthology/J98-3005.pdf)]

McKeown and Radev (1995) and Radev and McKeown (1998) are the pioneering work in Multi-Document Summarization--it's the first historical example of a MDS system. The system tackles single events about a narrow domain (news articles about terrorism) and produces a briefing merging relevant information about each event and how reports by different news agencies have evolved over time.


**Opinosis** [[paper](https://www.aclweb.org/anthology/C10-1039.pdf)]

Ganesan et al. (2010) employs a graph-based approach to abstractive summarization of highly redundant opinions.



## Additional Resources

-	Semantics for Semantic Parsing [[slides](https://yoavartzi.com/sp14/slides/steedman.sp14.pdf)]
-	Theories of Semantic Representation [[slides](https://www.clsp.jhu.edu/wp-content/uploads/2018/06/2018-06-21-Ellie-Pavlick-JSALT-Summer-School.pdf)]
-	SQL-Based Semantic Parsing [[website](https://medium.com/@tao.yu/awesome-sequence-to-sql-and-semantic-parsing-1d7656861679/)]
-	AllenAI Semantic Parsing Tutorial (ACL 2018) [[website](https://github.com/allenai/acl2018-semantic-parsing-tutorial)]
-	SEMPRE [[website](https://nlp.stanford.edu/software/sempre/)]
-	NLP Progress for Semantic Parsing [[website](https://nlpprogress.com/english/semantic_parsing.html/)]
