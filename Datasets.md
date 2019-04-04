## Datasets
#### QA
1. [**NQ**] Natural Questions: a Benchmark for Question Answering Research.** Tom Kwiatkowski and Michael Collins, Research Scientists, Google AI Language. January 23, 2019. [paper](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/b8c26e4347adc3453c15d96a09e6f7f102293f71.pdf); [blog](https://ai.google.com/research/NaturalQuestions/dataset)
2. [**SQuAD 2.0: Stanford Question Answering Dataset**] Know What You Don’t Know: Unanswerable Questions for SQuAD. Pranav Rajpurkar∗ Robin Jia∗ Percy Liang. 2018 ACL. 
3. [**SQuAD 1.0: Stanford Question Answering Dataset**] SQuAD: 100,000+ Questions for Machine Comprehension of Text. Pranav Rajpurkar, Jian Zhang, Konstantin Lopyrev, Percy Liang. 2016 EMNLP.
4. [**HotpotQA**]
5. [**NarrativeQA**]
6. [**TriviaQA**]
7. [**QuAC**]
8. [**CoQA**]
9. [**WikiQA**]
10. [**MS Marco**]
11. [**NewsQA**]
12. [**CNN/DailyMail news**] Teaching machines to read and comprehend. ACL 2015.
13. [**CBTest: Children’s Book Test**] The goldilocks principle: Reading children’s books with explicit memory representations. Hill et al. 2015. 
14. [**DuReader**] DuReader: a Chinese Machine Reading Comprehension Dataset from Real-world Applications. Haifeng Wang et al. 2018. [Leadboard](https://ai.baidu.com/broad/leaderboard?dataset=dureader)
15. [**CMRC 2018**] Chinese Machine Reading Comprehension. HIT & iFLYTEK 2018. [link](https://hfl-rc.github.io/cmrc2018/task/)
16. [**bAbI**] Towards AI-Complete Question Answering: A Set of Prerequisite Toy Tasks. Jason Weston 2015. 
17. [**Who-Did-What**] Who did What: A Large-Scale Person-Centered Cloze Dataset. 2016 EMNLP. Takeshi Onishi et al. 

#### Two Sentence Classification 
1. [**SNLI: Stanford Natural Language Inference**] A large annotated corpus for learning natural language inference. Bowman et al. 2015. [link]((https://nlp.stanford.edu/projects/snli/))
2. [**SciTail**] A textual entailment dataset from science question answering.  Khot et al. AAAI. 2018. [link]((https://leaderboard.allenai.org/scitail/submissions/public))
3. [**QQP: Quora Question Pairs**] Quora question pairs. Z. Chen, H. Zhang, X. Zhang, and L. Zhao. 2018. 
4. [**MRPC: Microsoft Research Paraphrase Corpus**] Automatically constructing a corpus of sentential paraphrases. William B Dolan and Chris Brockett. 2005.
5. [**MNLI: Multi-Genre Natural Language Inference**] The RepEval 2017 Shared Task: MultiGenre Natural Language Inference with Sentence Representations N. Nangia, A. Williams, A. Lazaridou, and S. R. Bowman. 2017.
6. [**RTE: Recognizing Textual Entailment**] Glue: A multi-task benchmark and analysis platform for natural language understanding. Alex Wang et al. 2018 
7. [**WNLI:  Winograd NLI**] derived from The winograd schema challenge. Hector Levesque et al. 2012.

#### Two Sentence Relevance
1. [**STS-B: Semantic Textual Similarity Benchmark**] Semeval-2017 task 1: Semantic textual similarity-multilingual and cross-lingual focused evaluation. Daniel Cer et al. 2017.
2. [**QNLI**] derived from the Stanford Question Answering Dataset.(SQuAD 1.0) 2016.

#### Sentence Classification
1. [**CoLA**] Neural Network Acceptability Judgments. Alex Warstadt, Amanpreet Singh, and Samuel R Bowman. 2018
2. [**SST-2: Stanford Sentiment Treebank**] Recursive deep models for semantic compositionality over a sentiment treebank. Richard Socher et al. 2013 EMNLP.


## Tasks [NLU models & NLI tasks]
1. **Single Sentence.** [a sentence can be an arbitrary span of contiguous text or word sequence, rather than a linguistically plausible sentence.]
    - single-sentence classification
        - CoLA (predict whether an English sentence is grammatically plausible.)
        - SST-2 (determine whether the sentiment of a sentence extracted from movie reviews is positive or negative)
   
2. **Pair Sentences.**
    - pairwise text classification
        - RTE (predict whether the hypothesis is an entailment, or not entailment with respect to the premise.)
        - MNLI (predict whether the hypothesis is an entailment, contradiction, or neutral with respect to the premise.)
        - WNLI (select the referent of a pronoun from a list of choices in a given sentence which contains the pronoun.)
        - QQP (predict whether two questions are semantically equivalent)
        - MRPC (whether a sentence pair is semantically equivalent to the other in the pair)
        - SNLI (widely used entailment dataset for NLI)
        - SciTail (assessing whether a given premise entails a given hypothesis)
    - text similarity scoring
        - STS-B (Given a pair of sentences, the model predicts a real-value score indicating the semantic similarity of the two sentences)
    - relevance ranking
        - QNLI (The task involves assessing whether a sentence contains the correct answer to a given query)
3. **QA.**
    - extractive QA
        - SQuAD 1.0 (extract answer from a context given a question)
        - SQuAD 2.0 (predict whether have answer and extract answer from a context given a question)
        - CNN/DailyMail News (to teach the machine to do cloze-style reading comprehensions)
    - generate QA
        - Conversational QA
            - pass
        - Single-turn QA
            - DuReader (summary answer from multiple documents according to question which type is in Entity/Description/YesNo or Fact/Opinion)

## Data process tools
1. [jackalhan/qa_datasets_converter](https://github.com/jackalhan/qa_datasets_converter)
    - Dataset Converter for natural language processing tasks such QA(question-answering) Tasks: from one format to other one. 


## Data scale comparison
| Corpus | Task | #Train | #Dev | #Test | #Label | Metrics | Category | Source | 
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| CoLA | Acceptablility | 8.5k | 1k | 1k | 2 | Matthews corr | Single-Sentence Classification(GLUE) | |
| SST-2 | Sentiment | 67k | 872 | 1.8k | 2 | Accuracy | Single-Sentence Classification(GLUE) | movie reviews |
| STS-B | Similarity | 7k | 1.5k | 1.4k | 1 | Pearson/Spearman corr | Text Similarity(GLUE) | multiple data resources |
| QNLI | QA/NLI | 108k | 5.7k | 5.7k | 2 | Accuracy | Relevance Ranking(GLUE) | SQuAD 1.0 |
| QQP | Paraphrase | 364k | 40k | 391k | 2 | Accuracy/F1 | Pairwise Text Classification(GLUE) | Quora |
| MRPC | Paraphrase | 3.7k | 408 | 1.7k | 2 | Accuracy/F1 | Pairwise Text Classification(GLUE) | online news | 
| MNLI | NLI | 393k | 20k | 20k | 3 | Accuracy | Pairwise Text Classification(GLUE) | | 
| RTE | NLI | 2.5k | 276 | 3k | 2 | Accuracy | Pairwise Text Classification(GLUE) | |
| WNLI | NLI | 634 | 71 | 146 | 2 | Accuracy | Pairwise Text Classification(GLUE) | |
| SNLI | NLI | 549k | 9.8k | 9.8k | 3 | Accuracy | Pairwise Text Classification | captions of the Flickr30 corpus |
| SciTail | NLI | 23.5k | 1.3k | 2.1k | 2 | Accuracy | Pairwise Text Classification | science questions & relevant web sentences |
| SQuAD 1.0 | QA | 87.5k | 10.5k | 9.5k | |  Accuracy/F1 | Extractive QA | 546 wiki pages |
| SQuAD 2.0 | QA | 130.3k | 11.8k | 8.8k | | Accuracy/F1 | Extractive QA | 348 wiki pages |
| NQ | QA | 307.3k | 7.8k | 7.8k | | | Extractive QA | Google Search Engine |
| CMRC 2018 | Span-Extraction Reading Comprehension | 11.1k | 3.2k | 2.5k | span | EM/F1 | Extractive QA | Chinese wiki papes |
| DuReader | Open-domain Question Answering | 271.5k | 10k | 20k | | [ROUGE-L and BLEU4](http://aclweb.org/anthology/W18-2611) | Generative QA |  Baidu Search & Baid Zhidao | 
| CNN/DailyMail | news |


## Data related links
1. [Baidu Release Chinese Dataset](https://ai.baidu.com/broad/introduction)
2. 

## References
1. Multi-Task Deep Neural Networks for Natural Language Understanding. Xiaodong Liu et al. 2019.
