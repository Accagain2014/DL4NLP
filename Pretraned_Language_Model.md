
## Papers

----
[1. Semi-supervised Sequence Learning](https://arxiv.org/abs/1511.01432)

- 2015 NIPS. Andrew M. Dai, Quoc V. Le. Google.
- use unlabeled data to do pretrain, and increase the skill for text classification
- how to use unlabeled data ? pretrain
    - language model manner, predict next word/token in the sequence
    - autoencoder, reads the input sequence into a vector and predicts the input sequence again.
- use the weights learned from unlabeled data to initialize the supervised methods

    
----
[2. Attention Is All You Need](https://papers.nips.cc/paper/7181-attention-is-all-you-need.pdf)
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
        
    
----
[3. Deep contextualized word representations](https://aclweb.org/anthology/N18-1202)
- ELMo. NAACL, 2018.

    
----
[4. Improving Language Understanding by Generative Pre-Training](https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf)
- OpenAI GPT (Radford et al., 2018)
- use transformer's decoder to do pretrain with language model loss, and then finetune with different tasks
- in finetune stage, convert all structured inputs into token sequences to be processed by pre-trained model, followed by a linear+softmax layer
- [blog](https://blog.openai.com/language-unsupervised/)
- [code](https://github.com/openai/finetune-transformer-lm)
    
    
----
[5. BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/pdf/1810.04805.pdf)
- 2018 . Google.
- (tensorflow version, but GPU training is single-GPU only.)[https://github.com/google-research/bert]
- bidirectional transformer + finetune
- the relation bettween bert and transform
    - bert use transformer's encoder layer
    - the model is constructed in modeling.py (class BertModel) and is pretty much identical to a vanilla Transformer encoder.

    
----
[6. Language Models are Unsupervised Multitask Learners](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf)
- 2019 OpenAI GPT-2.0. 
- Dateset: WebText. 更大数据和更大网络，LM评价上超过了大部分STOA, 尝试在不需要监督数据的情况下，对下游任务进行预测，超过了很多baseline.
- [openAI blog](https://blog.openai.com/better-language-models/)
- [117M model and code](https://github.com/openai/gpt-2)
- 问题：repetitive text, world modeling failures[常识错误], unnatural topic switching;
- “zero-shot” setting: Our model is not trained on any of the data specific to any of these tasks and is only evaluated on them as a final test
- not releasing the dataset, training code, or GPT-2 model weights.
- Zero-shot, BPM输入, 数据质量更好+数据更多+网络更深
- [张俊林, 效果惊人的GPT 2.0模型：它告诉了我们什么](https://zhuanlan.zhihu.com/p/56865533)
    
    
----
[7. Multi-Task Deep Neural Networks for Natural Language Understanding](https://arxiv.org/pdf/1901.11504.pdf)
- MSRA, MULTI-TASK DNN. Xiaodong Liu, Pengcheng He, Weizhu Chen, Jianfeng Gao. 2019.
- Based on Bert, finetune with multi-task objective. New STOA in 8 tasks of 9 tasks in Glue. Good generalization capability.
    
    
----  
[8. Pretraining-Based Natural Language Generation for Text Summarization.](https://arxiv.org/pdf/1902.09243.pdf)
- MSRA. 2019.
- 将bert应用于文本摘要, 提出two-stage思路：stage-one transformer出摘要草稿, stage-two tansformer带上原文refine.
- 针对Summary的评价标准Rouge增加了一个额外的loss, 机器内存小, batch_size不能设大, 多steps延迟更新.
    



    