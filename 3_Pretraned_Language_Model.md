
## Papers

[1. Semi-supervised Sequence Learning](https://arxiv.org/abs/1511.01432)
-----

- 2015 NIPS. Andrew M. Dai, Quoc V. Le. Google.
- use unlabeled data to do pretrain, and increase the skill for text classification
- how to use unlabeled data ? pretrain
    - language model manner, predict next word/token in the sequence
    - autoencoder, reads the input sequence into a vector and predicts the input sequence again.
- use the weights learned from unlabeled data to initialize the supervised methods



[2. Attention Is All You Need](https://papers.nips.cc/paper/7181-attention-is-all-you-need.pdf)
-----
- 2017 NIPS. Before BERT， Transformer. Google Brain.
- Only rely on Attention network, not rely on any RNN or CNN, good at parallelization, and have less train time.
- The biggest benefit, however, comes from how The Transformer lends itself to parallelization.
- understanding related
    - [**visual transformer**](https://jalammar.github.io/illustrated-transformer/)
- code related
    - [**Tensorflow offictal models: Transformer Translation Model**](https://github.com/tensorflow/models/tree/master/official/transformer)
    - [The Annotated Transformer. pytorch](http://nlp.seas.harvard.edu/2018/04/03/attention.html)
    - [tensor2tensor library. tf](https://github.com/tensorflow/tensor2tensor/blob/master/tensor2tensor/models/transformer.py)
    - [Easy Understantding by Kyubyong/transformer. tf](https://github.com/Kyubyong/transformer)
    - [Tensor2Tensor notebook](https://colab.research.google.com/github/tensorflow/tensor2tensor/blob/master/tensor2tensor/notebooks/hello_t2t.ipynb)
        
    
[3. Deep contextualized word representations](https://aclweb.org/anthology/N18-1202)
------
- ELMo. NAACL, 2018.

    
[4. Improving Language Understanding by Generative Pre-Training](https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf)
------
- OpenAI GPT (Radford et al., 2018)
- use transformer's decoder to do pretrain with language model loss, and then finetune with different tasks
- in finetune stage, convert all structured inputs into token sequences to be processed by pre-trained model, followed by a linear+softmax layer
- [blog](https://blog.openai.com/language-unsupervised/)
- [code](https://github.com/openai/finetune-transformer-lm)
    
       
[5. BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/pdf/1810.04805.pdf)
------
- 2018 . Google.
- (tensorflow version, but GPU training is single-GPU only.)[https://github.com/google-research/bert]
- bidirectional transformer + finetune
- the relation bettween bert and transform
    - bert use transformer's encoder layer
    - the model is constructed in modeling.py (class BertModel) and is pretty much identical to a vanilla Transformer encoder.
- base parameters(12 layers)
    - 108M (12 layers, hidden: 768, embedding: 768, 参数不共享)
- large parameters(24 layers)
    - 334M (24 layers, hidden: 1024, embedding: 1024, 参数不共享)
- xlarge
    - 1270M (24 layers, hidden: 2048, embedding: 2048, 参数不共享)


    
[6. Language Models are Unsupervised Multitask Learners](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf)
------
- 2019 OpenAI GPT-2.0. 
- Dateset: WebText. 更大数据和更大网络，LM评价上超过了大部分STOA, 尝试在不需要监督数据的情况下，对下游任务进行预测，超过了很多baseline.
- [openAI blog](https://blog.openai.com/better-language-models/)
- [117M model and code](https://github.com/openai/gpt-2)
- 问题：repetitive text, world modeling failures[常识错误], unnatural topic switching;
- “zero-shot” setting: Our model is not trained on any of the data specific to any of these tasks and is only evaluated on them as a final test
- not releasing the dataset, training code, or GPT-2 model weights.
- Zero-shot, BPM输入, 数据质量更好+数据更多+网络更深
- [张俊林, 效果惊人的GPT 2.0模型：它告诉了我们什么](https://zhuanlan.zhihu.com/p/56865533)
    
    
[7. Transformer-XL: Attentive Language Models Beyond a Fixed-Length Context](https://arxiv.org/pdf/1901.02860.pdf)
------
- 2019 CMU & Google Brain.
- contributions
    - a segment-level recurrence mechanism and a relative positional encoding scheme.
- codes
    - official code, pytorch & tf: [kimiyoung/transformer-xl](https://github.com/kimiyoung/transformer-xl)
- blogs
    - officail blog: [Transformer-XL: Unleashing the Potential of Attention Models](https://ai.googleblog.com/2019/01/transformer-xl-unleashing-potential-of.html)
- applications
    - word-level language modeling
    - character-level language modeling
    - generate relatively coherent long text articles with thousands of tokens trained on only 100M tokens
   

[8. RoBERTa: A robustly optimized BERT pretraining approach]
------
- todo
- 2019, Yinhan Liu & ... & Danqi Chen.



[9. XLNet: Generalized Autoregressive Pretraining for Language Understanding]
------
- todo
- 2019 Yang et al.
- code
    - Chinese
        - [ymcui/Chinese-PreTrained-XLNet](https://github.com/ymcui/Chinese-PreTrained-XLNet)
    - English
        - [officail: zihangdai/xlnet](https://github.com/zihangdai/xlnet)



[10. BERT-wwm-ext, Pre-Training with Whole Word Masking for Chinese BERT]()
------
- todo
 
  
    
[11. A Lite Bert For Self-Supervised Learning Language Representations ]
------
- done
- contributions
    - reduce parameters
        - width, decomposing the large vocabulary embedding matrix into two small matrices.
        - deep, cross-layer parameter sharing.
        - parameters:
            - base: 12M, layers: 12, hidden: 768, embedding: 128, share parameter
            - large: 18M, layers: 24, hidden: 1024, embedding: 128, share parameter
            - xlarge: 59M, layers: 24, hidden: 2048, embedding: 128, share parameter
            - xxlarge: 233M, layers: 12, hidden: 4096, embedding: 128, share parameter        
    - loss
        - a self-supervised loss for sentence-order prediction(SOP), which primary focuses on inter-sentence coherence. 
        to address the ineffectiveness of the next sentence prediction(NSP) loss in original BERT. 
    
    - others
        - remove dropout to enlarge capacity of model. (train losts of steps but not to overfit in training data)
        - use LAMB as optimizer to train with big batch size
        - use n-gram (P(uni-gram) > P(bi-gram) > P(tri-gram)) as masked language model. 
- codes
    - Chinese
        - [brightmart/albert_zh](https://github.com/brightmart/albert_zh)
        - 

    
### Applications 
[1. Pretraining-Based Natural Language Generation for Text Summarization.](https://arxiv.org/pdf/1902.09243.pdf)
------
- MSRA. 2019.
- 将bert应用于文本摘要, 提出two-stage思路：stage-one transformer出摘要草稿, stage-two tansformer带上原文refine.
- 针对Summary的评价标准Rouge增加了一个额外的loss, 机器内存小, batch_size不能设大, 多steps延迟更新.
    


### Acceleration
[1. LAMB: LARGE BATCH OPTIMIZATION FOR DEEP LEARNING: TRAINING BERT IN 76 MINUTES]
------
- todo
- 2019.


### Surveys
[1. ]
 