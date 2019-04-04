# Deep Learning for NLP
Understanding Classic Deep Learning NLP Methods and their Implementations.

## Important Links
1. [thunlp/RCPapers](https://github.com/thunlp/RCPapers)
2. [Overview of Modern Deep Learning Techniques Applied to Natural Language Processing](https://github.com/omarsar/nlp_overview)

## Important Agencies
1. [Google AI]
    - Transformer
    - Bert
2. [Open AI](https://openai.com/blog/)
    - GPT1.0/2.0
3. MSRA
    - MT-DNN


## Papers

- [1. Attention Is All You Need](https://papers.nips.cc/paper/7181-attention-is-all-you-need.pdf)
    - 2017 NIPS. BERT之前， Transformer. Google Brain.
    - [The Annotated Transformer](http://nlp.seas.harvard.edu/2018/04/03/attention.html)
    - [tensor2tensor library](https://github.com/tensorflow/tensor2tensor)
    - [易懂的Kyubyong/transformer](https://github.com/Kyubyong/transformer)
    - 只依赖Attention的网络, 不依靠RNN和CNN。并行化更高，训练时间短。
    - [可视化transformer](https://jalammar.github.io/illustrated-transformer/)
    
   
- [2. Semi-supervised Sequence Learning](https://arxiv.org/abs/1511.01432)
    - 2015 NIPS. Andrew M. Dai, Quoc V. Le. Google.
    - 利用未标注的数据进行预训，提高文本分类的能力
    - 怎样利用未标注的数据？ pretrain
        - 语言模型的方式，预测序列中的下一个
        - 使用一个序列的autoencoder, reads the input sequence into a vector and predicts the input sequence again.
    - 利用未标注数据学习到的权重，给监督学习算法初始化参数
    
    
- [3. Improving Language Understanding by Generative Pre-Training](https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf)
    - OpenAI GPT (Radford et al., 2018)
    - [blog](https://blog.openai.com/language-unsupervised/)
    - [code](https://github.com/openai/finetune-transformer-lm)
    

- [4. BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/pdf/1810.04805.pdf)
   - 2018 . Google.
   - (tensorflow version, but GPU training is single-GPU only.)[https://github.com/google-research/bert]
   - 双向transformer + finetune


- [5. Language Models are Unsupervised Multitask Learners](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf)
    - 2019 OpenAI GPT-2.0. 
    - Dateset: WebText. 更大数据和更大网络，LM评价上超过了大部分STOA, 尝试在不需要监督数据的情况下，对下游任务进行预测，超过了很多baseline.
    - [openAI blog](https://blog.openai.com/better-language-models/)
    - [117M model and code](https://github.com/openai/gpt-2)
    - 问题：repetitive text, world modeling failures[常识错误], unnatural topic switching;
    - “zero-shot” setting: Our model is not trained on any of the data specific to any of these tasks and is only evaluated on them as a final test
    - not releasing the dataset, training code, or GPT-2 model weights.
    - Zero-shot, BPM输入, 数据质量更好+数据更多+网络更深
    - [张俊林, 效果惊人的GPT 2.0模型：它告诉了我们什么](https://zhuanlan.zhihu.com/p/56865533)
    
    
- [6. Multi-Task Deep Neural Networks for Natural Language Understanding](https://arxiv.org/pdf/1901.11504.pdf)
    - MSRA, MULTI-TASK DNN. Xiaodong Liu, Pengcheng He, Weizhu Chen, Jianfeng Gao. 2019.
    - Based on Bert, finetune with multi-task objective. New STOA in 8 tasks of 9 tasks in Glue. Good generalization capability.
    
    
- [7. Read + Verify: Machine Reading Comprehension with Unanswerable Questions. (2018 Dongsheng Li et al.)](https://arxiv.org/abs/1808.05759)
    - **Answerability** (whether the question has ans answer) & **Legitimacy** (whether the extracted text can be supported by the passage and the question)
    - Provide A Verifier to Judge Whether Have A Answer by  Modeling Local Answer Sentence Information.
    - Provide 2 auxiliary losses. One is for plausible answer reinforce, another is for classification reinforce.
    - SQuAD 2.0 Test F1 score: 74.2 (the state of art model of Aug. 28th, 2018)

- [8. U-Net: Machine Reading Comprehension with Unanswerable Questions. (2018 Xipeng Qiu†∗, Yang Liu‡ et al.)](https://arxiv.org/abs/1810.06638)
    - SQuAD 2.0 Test F1 score: 71.7.
    - 
    
- [9. Pretraining-Based Natural Language Generation for Text Summarization.](https://arxiv.org/pdf/1902.09243.pdf)
    - MSRA. 2019.
    - 将bert应用于文本摘要, 提出two-stage思路：stage-one transformer出摘要草稿, stage-two tansformer带上原文refine.
    - 针对Summary的评价标准Rouge增加了一个额外的loss, 机器内存小, batch_size不能设大, 多steps延迟更新.
    


## QA Models
- Match-LSTM
- BiDAF, Bi-Directional attention flow for machine comprehension. 2017 ICLR. MInjoon Seo et al. University of Washington & Allen Institute for Artificial Intelligence.
- AoA Reader
- DCN
- R-net: Machine reading comprehension with self matching networks. [code](https://github.com/HKUST-KnowComp/R-Net) MSRA. 2018.
- QANET: COMBINING LOCAL CONVOLUTION WITH GLOBAL SELF-ATTENTION FOR READING COMPREHENSION. [code](https://github.com/NLPLearn/QANet) CMU & Google Brain 2018.  Adams Wei Yu1, David Dohan2, Minh-Thang Luong
- AoA: Attention-over-Attention Neural Networks for Reading Comprehension. Yiming Cui et al. HIT & iFLYTEK. 2017. 
- Text Understanding with the Attention Sum Reader Network. ACL 2016. IBM Watson. 
- 
- **1. Multi-task Learning with Sample Re-weighting for Machine Reading Comprehension.** [code](https://github.com/xycforgithub/MultiTask-MRC). MS & CMU Yichong Yu et al. 2019.
    - MTL-task applied to MRC
    - sample re-weighting scheme. add corpus similarity to final loss.
    - model is complicated.
    
- 