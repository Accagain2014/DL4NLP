
### Categories
- text classification
- sentiment analysis


### Methods
#### Fasttext
- hierarchical softmax
    - K classes, N is hidden size
    - O(K*N) -> O(logK*N), when V is large, can speed up a lot
    - Inference time: DFS with Tree Pruning, O(N*log(K))
    - When K is more than 300K here
- very very fast and simple

#### TextCNN
- very classic methods


#### Bert


### Papers
- Bag of Tricks for Efficient Text Classification. (2016, Facebook AI Research, Fasttext)



### Dataset
- Chinese
    - [THUCNews](https://aistudio.baidu.com/aistudio/competition/detail/10)
        - THUCNews是根据新浪新闻RSS订阅频道2005~2011年间的历史数据筛选过滤生成，包含74万篇新闻文档, 14个大类; 
        - 财经、彩票、房产、股票、家居、教育、科技、社会、时尚、时政、体育、星座、游戏、娱乐;
        - http://thuctc.thunlp.org/
    
    - [haiker2011/awesome-nlp-sentiment-analysis](https://github.com/haiker2011/awesome-nlp-sentiment-analysis)
        - 收集NLP领域相关的数据集、论文、开源实现，尤其是情感分析、情绪原因识别、评价对象和评价词抽取等方面。
  

### Tricks
- https://www.zhihu.com/question/265357659
- 分词影响
    - 确保分词器与词向量表中的token粒度match其实是更更重要的事情！毕竟哪怕你词分的再好，一旦词向量表里没有的话，那么就变成OOV了，分的再好也木用了
    - 分词器和词向量对应
- 显然问题fasttext，简单问题CNN，复杂问题RNN，终极问题bert
- 数据增强，drop，shuffle，replace，近义词，扩充，截取（CCF 360人机大战，kaggle Quora）
- dropout和BN
