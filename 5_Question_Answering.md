## QA Models
- Match-LSTM
- BiDAF, Bi-Directional attention flow for machine comprehension. 2017 ICLR. MInjoon Seo et al. University of Washington & Allen Institute for Artificial Intelligence.
- AoA Reader
- DCN
- R-net: Machine reading comprehension with self matching networks. [code](https://github.com/HKUST-KnowComp/R-Net) MSRA. 2018.
- QANET: COMBINING LOCAL CONVOLUTION WITH GLOBAL SELF-ATTENTION FOR READING COMPREHENSION. [code](https://github.com/NLPLearn/QANet) CMU & Google Brain 2018.  Adams Wei Yu1, David Dohan2, Minh-Thang Luong
- AoA: Attention-over-Attention Neural Networks for Reading Comprehension. Yiming Cui et al. HIT & iFLYTEK. 2017. 
- Text Understanding with the Attention Sum Reader Network. ACL 2016. IBM Watson. 


## Papers
- [1. Multi-task Learning with Sample Re-weighting for Machine Reading Comprehension.]() MS & CMU Yichong Yu et al. 2019.
    - [code](https://github.com/xycforgithub/MultiTask-MRC). 
    - MTL-task applied to MRC
    - sample re-weighting scheme. add corpus similarity to final loss.
    - model is complicated.
    
- [2. Read + Verify: Machine Reading Comprehension with Unanswerable Questions. (2018 Dongsheng Li et al.)](https://arxiv.org/abs/1808.05759)
    - **Answerability** (whether the question has ans answer) & **Legitimacy** (whether the extracted text can be supported by the passage and the question)
    - Provide A Verifier to Judge Whether Have A Answer by  Modeling Local Answer Sentence Information.
    - Provide 2 auxiliary losses. One is for plausible answer reinforce, another is for classification reinforce.
    - SQuAD 2.0 Test F1 score: 74.2 (the state of art model of Aug. 28th, 2018)

- [3. U-Net: Machine Reading Comprehension with Unanswerable Questions. (2018 Xipeng Qiu†∗, Yang Liu‡ et al.)](https://arxiv.org/abs/1810.06638)
    - SQuAD 2.0 Test F1 score: 71.7.
    

## Summary
- [Github: seriousran/awesome-qa](https://github.com/seriousran/awesome-qa)