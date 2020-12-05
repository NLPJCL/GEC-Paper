# GEC-Reading-List

This is a grammatical error correction reading list maintained by the HIT-LA Research Group.

------

| Content                              |
| ------------------------------------ |
| 1. [Shared Task](#1)                 |
| 2. [Dataset](#2)                     |
| 3. [Evaluation](#evaluation)         |
| 4. [SMT & NMT](#SMT)                 |
| 5. [NMT](#NMT)                       |
| 6. [Language Model](#Pretrain)       |
| 7. [Others(DA & MT)](#DA & MT)       |
| 8. [BEA 2019 Shared Task](#BEA)      |
| 9. [Non Autoregressive Model](#NAM)  |
| 10.[Spelling Error Correction](#SEC) |
| 11.[CGED2020](#CGED)                 |

<h2 id="shared_task"> Shared Task </h2>

- Ng Hwee Tou, Wu Siew Mei, Briscoe Ted, Hadiwinoto Christian, Susanto Raymond Hendy and Bryant Christopher. 2014. [The CoNLL-2014 Shared Task on Grammatical Error Correction](https://www.aclweb.org/anthology/W14-1701). In Proceedings of the Eighteenth Conference on Computational Natural Language Learning: Shared Task.
- Christopher Bryant, Mariano Felice, Øistein Andersen and Ted Briscoe. 2019. [Building Educational Applications 2019 Shared Task:Grammatical Error Correction](https://www.aclweb.org/anthology/W19-4406).

<h2 id="dataset"> Dataset </h2>

- Sylviane Granger. 1998. [The computer learner corpus: A versatile new source of data for SLA research](https://www.researchgate.net/profile/Sylviane_Granger/publication/237128463_The_computer_learner_corpus_A_versatile_new_source_of_data_for_SLA_research/links/0c96051dc1c596def1000000/The-computer-learner-corpus-A-versatile-new-source-of-data-for-SLA-research.pdf). Learner English on Computer. (LOCNESS)
- Mizumoto Tomoya, Komachi Mamoru, Nagata Masaaki and Matsumoto Yuji. 2011. [Mining revision log of language learning SNS for automated Japanese error correction of second language learners](https://www.aclweb.org/anthology/I11-1017). In Proceedings of 5th International Joint Conference on Natural Language Processing. (lang-8)
- Dahlmeier Daniel, Ng Hwee Tou and Wu Siew Mei. 2013. [Building a large annotated corpus of learner English: The NUS corpus of learner English](https://www.aclweb.org/anthology/W13-1703). In Proceedings of the eighth workshop on innovative use of NLP for building educational applications. (NUCLE)
- Napoles Courtney, Sakaguchi Keisuke and Tetreault Joel. 2017. [JFLEG: A fluency corpus and benchmark for grammatical error correction](https://arxiv.org/pdf/1702.04066.pdf). (JFLEG)
- Yannakoudakis Helen, Briscoe Ted and Medlock Ben. 2011. [A new dataset and method for automatically grading ESOL texts](https://dl.acm.org/citation.cfm?id=2002496).  In Proceedings of the 49th Annual Meeting of the Association for Computational Linguistics: Human Language Technologies. (FCE)
- Yannakoudakis Helen, Andersen Øistein E, Geranpayeh Ardeshir, Briscoe Ted and Nicholls Diane. 2018. [Developing an automated writing placement system for ESL learners](https://www.tandfonline.com/doi/abs/10.1080/08957347.2018.1464447). Applied Measurement in Education. (W&I)

<h2 id="evaluation"> Evaluation </h2>

- Dahlmeier Daniel and Ng Hwee Tou. 2012. [Better evaluation for grammatical error correction](https://dl.acm.org/citation.cfm?id=2382118). In Proceedings of the 2012 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies. (Maxmatch,M2)

  概述：提出了语法纠错模型的评价指标Maxmatch(M2).提出一种算法来从错误的句子和系统纠正的句子中抽取与人类标注的glod的edit最大匹配的系统edits。1)使用Levenshtein distance算法来确定从一个字符串到另外一个字符串的最短距离。列出一个Levenshtein matrix。从左上角到右下角的一条最短路径（操作）即是从错误句子到系统纠正句子所需要的最小操作。因为存在权值相等的边，因此最短路径不唯一。	

   2）因此我们对Levenshtein matrix进行改变它匹配在gold标准中的权值为负。使得选择的路径尽可能包括gold中的编辑。这就是Max Match名字的来源。

- Bryant Christopher, Felice Mariano, Briscoe Edward John. 2017. [Automatic annotation and evaluation of error types for grammatical error correction](https://www.aclweb.org/anthology/P17-1074). In Proceedings of the 55th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers).(ERRANT)

<h2 id="SMT"> SMT & NMT </h2>



<h2 id="NMT"> NMT </h2>

- Zhao Wei, Wang Liang, Shen Kewei, Jia Ruoyu, Liu Jingming. 2019. [Improving Grammatical Error Correction via Pre-Training a Copy-Augmented Architecture with Unlabeled Data](https://arxiv.org/pdf/1903.00138.pdf).

<h2 id="Pretrain"> Language Model </h2>

- Masahiro Kaneko, Masato Mita, Shun Kiyono, Jun Suzuki, Kentaro Inui. 2020. [Encoder-Decoder Models Can Benefit from Pre-trained Masked Language Models in Grammatical Error Correction](https://arxiv.org/pdf/2005.00987.pdf). In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics, pages 4248–4254 July 5 - 10, 2020. c 2020 Association for Computational Linguistics.(BERT)
- Satoru Katsumata，and Mamoru Komachi.2020. [Stronger Baselines for Grammatical Error Correction Using a Pretrained Encoder–Decoder Model](https://arxiv.org/pdf/2005.11849.pdf).In Proceedings of AACL-IJCNLP 2020 (BART,mBART)(BART)

​       概述：使用Bart预训练好的模型作为GECseq2seq任务的初始化参数，然后在具体任务上微调。

- Hongfei Wang, Michiki Kurosawa, Satoru Katsumata and Mamoru Komachi. 2020. [Chinese Grammatical Correction Using BERT-based Pre-trained Model](https://arxiv.org/pdf/2011.02093.pdf). In Proceedings of AACL-IJCNLP 2020.(BERT-Chinese)

  概述：使用bert-fuse和bert初始化seq2seq的方式对模型进行

- Mengyun Chen， Tao Ge， Xingxing Zhang， Furu Wei and Ming Zhou.2020[Improving the Efficiency of Grammatical Error Correction with Erroneous Span Detection and Correction](https://arxiv.org/pdf/2010.03260.pdf).EMNLP

  概述：微软亚洲研究院的 Ge Tao发表在2020EMNLP的作者，Ge Tao也是2018年ACL流畅度提升的作者，近几年一直钻研这个方向。本篇文章主要的动机是：序列到序列模型生成全部文本对于原序列与目标序列有很多重复序列的任务太浪费时间。所以提出了一种与语言无关的方法提高效率：把纠正任务分成两个阶段，ESD(错误的span检查)和ESC（错误的span纠正），其实ESC阶段只做上一阶段检查出来错误的span的纠正。ESD（错误的span检查）：当作一个序列标注任务(2分类问题)，每个token分类的类别是0或1，错误的token会输出1，正确的token会输出0.如果连续输出几个1，那么就认为这几个token就是一个错误的span。ESC（错误的span纠正）：输入是源句子并对错误的span替换为<s1> span </s1>，输出是仅仅生成错误span的纠正。因为还是用序列到序列的模型来纠正，因此是语言独立的。而作者提到，PIE和Gector因为涉及很多英语独有的词性变化，因此很难迁移到其他语言。（不一定对，可以针对汉语指定特殊的编辑操作. PIE论文做过消融实验，在英语中少了transformations，找回来下降了6.3，$F_{0.5}$下降了5.7）

<h2 id="(DA & MT)"> Others(DA & MT) </h2>

- Lichtarge Jared, Alberti Chris, Kumar Shankar, Shazeer Noam, Parmar Niki, Tong Simon. 2019. [Corpora Generation for Grammatical Error Correction](https://arxiv.org/pdf/1904.05780.pdf). Arxiv.
- Ge Tao, Wei Furu, Zhou Ming. 2018. [Fluency Boost Learning and Inference for Neural Grammatical Error Correction](https://www.aclweb.org/anthology/P18-1097). In Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers).
- Bryant Christopher, Briscoe Ted. 2018. [Language Model Based Grammatical Error Correction without Annotated Training Data](https://www.aclweb.org/anthology/W18-0529). In Proceedings of the Thirteenth Workshop on Innovative Use of NLP for Building Educational Applications.
- Rico Sennrich, Barry Haddow, and Alexandra Birch. 2016. [Neural Machine Translation of Rare Words with Subword Units](https://arxiv.org/pdf/1508.07909.pdf). In Proceedings of the 54th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers). Association for Computational Linguistics, Berlin, Germany, pages 1715–1725.(BPE)

<h2 id="BEA">BEA 2019 Shared Task</h2>

- Roman Grundkiewicz, Marcin Junczys-Dowmunt, and Kenneth Heafield. 2019. [Neural Grammatical Error Correction Systems with Unsupervised Pre-training on Synthetic Data](https://www.aclweb.org/anthology/W19-4427). In Proceedings of the 14th Workshop on Innovative Use of NLP for Building Educational Applications. Association for Computational Linguistics.（No. 1）
- Yo Joong Choe, Jiyeon Ham, Kyubyong Park, and Yeoil Yoon. 2019. [A Neural Grammatical Error Correction System Built On Better Pre-training and Sequential Transfer Learning](https://arxiv.org/pdf/1907.01256.pdf).  In Proceedings of the
  14th Workshop on Innovative Use of NLP for Building Educational Applications. Association for Computational Linguistics.（No. 2）
- Yoav Kantor, Yoav Katz, Leshem Choshen, Edo Cohen-Karlik, Naftali Liberman, Assaf Toledo, Amir Menczel, and Noam Slonim. 2019. [Learning to combine Grammatical Error Corrections](https://arxiv.org/pdf/1906.03897.pdf).  In Proceedings of the 14th Workshop on Innovative Use of NLP for Building Educational Applications. Association for Computational Linguistics. （No. 13）

<h2 id="NAM"> Non Autoregressive Model </h2>

- Kostiantyn Omelianchuk, Vitaliy Atrasevych, Artem Chernodub, Oleksandr Skurzhanskyi. 2020. [GECToR – Grammatical Error Correction: Tag, Not Rewrite](https://arxiv.org/pdf/2005.12592.pdf). in Proceedings of the 15th Workshop on Innovative Use of NLP for Building Educational Applications, pages 163–170. Association for Computational Linguistics.

- Abhijeet Awasthi, Sunita Sarawagi , Rasna Goyal , Sabyasachi Ghosh , Vihari Piratla. 2019. [Parallel Iterative Edit Models for Local Sequence Transduction](https://www.aclweb.org/anthology/D19-1435.pdf). In Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing, pages 4260–4270, Hong Kong, China. Association for Computational Linguistics.

- Felix Stahlberg, Shankar Kumar，2020.[Seq2Edits: Sequence Transduction Using Span-level Edit Operations](https://www.aclweb.org/anthology/2020.emnlp-main.418.pdf).EMNLP.

  概述：google Research在EMNLP2020发表的一篇文章，把高重叠的序列到序列任务转换成序列到编辑编辑任务。编辑的粒度是针对span(源序列的好几个词)。一个编辑操作是:(t,p,n),t:错误类型，p是原序列结束位置(自动从上一个结束的位置开始)，n是不变或者纠正。用的是类似transfomer架构，预测span(position)用的是pointer network.有两个decoderA和B。值得借鉴的是：google针对这种特定问题，源序列和目标序列大体一致时，选择网络结构的
  
  原因。这里用到了pointer network。没有深入了解，以后可以仔细看看。实验结果一般。

<h2 id="SER"> Spelling Error Correction </h2>

- Zuyi Bao, Chen Li and Rui Wang.2020.[Chunk-based Chinese Spelling Check with Global Optimization](https://www.aclweb.org/anthology/2020.findings-emnlp.184.pdf),EMNLP-Findings.
- Shaohua Zhang1 , Haoran Huang1 , Jicong Liu2 and Hang Li1.2020.[Spelling Error Correction with Soft-Masked BERT](https://www.aclweb.org/anthology/2020.acl-main.82.pdf).ACL.

<h2 id="CGED"> CGED2020 </h2>

