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


## Neural Methods

**Using Graph Convolutional Network** [[paper](https://www.aclweb.org/anthology/K17-1045/)]

Yasunaga et al., 2017 exploits the graph structure among discourse relations in text clusters and uses a graph convolutional network (GCN) on the relation graphs to generate high-level hidden sentence features for salience estimation. The input node features are sentence embeddings from Recurrent Neural Networks (RNNs). It uses a greedy heuristic to extract salient sentences and demonstrates improvement from traditional graph-based extractive approaches as well as the vanilla sequence model (specifically GRU) with no graph.


**SDS to MDS** [[paper](https://www.aclweb.org/anthology/K17-1045/)]

Zhang et al. (2018) adds an additional document-level encoding to adapt a hierarchical encoding framework trained on Single-Document Summarization data to Multi-Document Summarization.


**SDS to MDS with MMR** [[paper](https://www.aclweb.org/anthology/D18-1446.pdf)]

Lebanoff et al. (2018) introduces an external MMR module that doesn't require training on the MDS, to apply encoder-decoder models trained on SDS data to MDS.


## Evaluation

**ROUGE** [[paper](https://www.aclweb.org/anthology/W04-1013.pdf)]

Lin (2004) introduces ROUGE--Recall-Oriented Understudy for Gisting Evaluationm which contains a set of metrics that have become the standards for evaluating summarization tasks. Commonly used ROUGE scores include ROUGE-N, which uses n-gram recall, as well as ROUGE-L, which is based on longest common subsequence. The paper is one of the most cited papers in NLP.


**Normalized ROUGE** [[paper](https://www.aclweb.org/anthology/W19-2303/)]

Sun et al. (2019) shows that ROUGE is highly sensitive to summary length, thus giving unfair advantage to methods that produce longer summaries. They propose an alternative metric that normalize ROUGE scores with those from a random system producing summaries of the same length.


**Better Correlation with Human Evaluation** [[paper](https://arxiv.org/pdf/1905.13322.pdf)]

Goodrich (2019) proposes an alternative metric that correlates with human evaluation of factual accuracy better.

